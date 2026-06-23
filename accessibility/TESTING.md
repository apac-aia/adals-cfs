# 如何重新測試這個頁面

改過 `index.html` 之後，任何人都可以照這份自己重測 https://speakers.apac-aia.org/ 。
下面以「瀏覽器、免安裝或裝個擴充」的方式為主，非工程師也能跑；工程師路線（指令列）放最後。

## 兩個共同前提

1. **淺色和深色都要測。** 頁面右上角的圓形按鈕可以切換主題，兩種模式各測一次。
2. **順手看一下窄螢幕。** 按 `F12` 開開發者工具，點裝置圖示（手機/平板切換）選 320 寬，確認沒有左右橫向捲動。

通過的大原則：**沒有 Error、對比都過、鍵盤能操作、報讀器讀得到。**

---

## 1. WAVE（最簡單，先測這個）

WAVE 是 WebAIM 出的網頁無障礙檢測工具，會把問題直接標在頁面上。

**做法 A（免安裝）：** 開 https://wave.webaim.org/ ，把網址 `https://speakers.apac-aia.org/` 貼進去，按下去。
**做法 B（裝擴充，可測深色）：** 安裝「WAVE Evaluation Tool」瀏覽器擴充，開頁面後點它的圖示。要測深色，先把頁面切到深色再點。

**看左側這幾個數字：**
- **Errors = 0**、**Contrast Errors = 0** → 通過。
- **Alerts** 是「建議」不是錯誤（例如 "Possible heading"），可以接受。
- 參考：目前淺色和深色都是 0 Errors、0 Contrast Errors、AIM Score 10/10。

---

## 2. Lighthouse（Chrome 內建，測效能加無障礙加 SEO）

Lighthouse 是 Chrome 內建的網站品質檢測，不用安裝。

1. 用 Chrome 開頁面 → 按 `F12` → 上方分頁找 **Lighthouse**。
2. 勾選 **Performance / Accessibility / Best Practices / SEO**，Mode 選 Navigation，按 **Analyze page load**。

**通過標準：**
- **Accessibility、Best Practices、SEO 應該是 100。**
- Performance：桌機模式（Desktop）應接近 100；手機模式（Mobile）分數天生較低，那是它刻意模擬「慢手機加慢網路」，90 以上就很好，不用追到 100。

---

## 3. axe DevTools（抓 WCAG 違規，給想更嚴謹的人）

axe 是 Deque 出的無障礙檢測引擎，業界常用。

1. 安裝「axe DevTools」瀏覽器擴充。
2. 開頁面 → `F12` → 分頁找 **axe DevTools** → 按 **Scan ALL of my page**。

**通過標準：Violations（違規）= 0。** 淺色和深色各掃一次。

---

## 4. 視覺模擬（色覺缺陷或低視力）

- **看現成的：** https://speakers.apac-aia.org/accessibility/vision-sim/ 已經有 6 種視覺條件乘以淺色深色的對照圖。
- **自己模擬色盲：** Chrome 按 `F12` → 右上 `⋮` → More tools → **Rendering** → 找 **Emulate vision deficiencies**，選不同色覺類型看頁面。
- **低視力或老花：** 用瀏覽器放大到 200%（`Ctrl` 加 `+`），確認文字不會被切掉或重疊。

判斷重點：**就算去掉顏色或模糊掉，標題、內文、按鈕還是讀得懂、認得出。** 這頁靠的是明暗對比，不是只靠顏色。

---

## 進階：指令列（工程師）

裝好 Node 後，在 repo 目錄執行：

```bash
# Lighthouse (add --preset=desktop for the desktop score)
npx lighthouse https://speakers.apac-aia.org \
  --only-categories=performance,accessibility,best-practices,seo --output=html

# axe-core: inject axe.min.js in the browser console, then run axe.run()
```

---

測完若想留紀錄，把結果更新到同資料夾的 `audit.md`。

<!-- writing-harness: S0/S1/S2 ok 2026-06-24 -->
