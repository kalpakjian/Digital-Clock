# Digital-Clock

這是一個 Unity 練習專案，使用 **Unity Visual Scripting** 製作的 3D 數字時鐘。場景中有三個獨立的數字顯示器（個位、十位、百位），每秒自動遞增計數，從 0 計數至 999。

## 專案說明

本專案以 Unity Visual Scripting（視覺化腳本）實現計時邏輯，無需撰寫 C# 程式碼。計時器透過 `Time.deltaTime` 累積時間，每達到 1 秒便將計數值加一，再將計數值拆分為個位、十位、百位三組數字，各自控制對應的 3D 數字 GameObject 顯示（`SetActive`）。計數上限為 999，達到上限後停止。

## 開發環境

- Unity 版本：`2022.3.62f3`
- 渲染管線：Universal Render Pipeline（URP）
- 專案類型：Unity Visual Scripting 練習專案
- 主要練習內容：
  - Unity Visual Scripting 流程圖（Flow Graph）設計
  - 使用 `Time.deltaTime` 實作計時器
  - 整數拆位運算（除法、取餘數）
  - 透過 `SetActive` 控制多個 GameObject 顯示 / 隱藏
  - Subgraph（子圖）封裝重複邏輯

## 功能特色

- 3D 數字顯示（FBX 模型：`Numbers.fbx`），共 10 個數字形狀（0–9）
- 三位數顯示：個位（`onesList`）、十位（`tensList`）、百位（`hunderredsList`）
- 每秒自動遞增，計數範圍 0–999
- 使用獨立材質（`A.mat`、`A 1.mat` … `A 9.mat`）對應各數字外觀
- 完全由 Visual Scripting 驅動，無 C# 腳本

## 專案結構

```
Digital-Clock/
├── Assets/
│   ├── DigitalTimer.unity          # 主場景
│   ├── Numbers.fbx                 # 數字 0–9 的 3D 模型
│   ├── Cube.prefab                 # 基礎 Cube Prefab
│   ├── demo prefab/                # 示範用 Prefab 資料夾
│   ├── digitalClock.asset          # 主 Visual Scripting 圖（計時 + 顯示邏輯）
│   ├── digit0.asset                # 個位數字 Visual Script
│   ├── digit1.asset                # 十位數字 Visual Script
│   ├── digit2.asset                # 百位數字 Visual Script
│   ├── A.mat / A 1.mat … A 9.mat  # 數字 0–9 對應材質
│   ├── Scenes/                     # 場景設定資料夾
│   ├── Settings/                   # URP 渲染設定
│   └── Unity.VisualScripting.Generated/  # Visual Scripting 自動生成程式碼
├── Packages/                       # Unity Package 設定
├── ProjectSettings/                # 專案設定
├── .gitattributes
├── .gitignore
└── README.md
```

## 下載專案

先使用 Git 將專案複製到本機：

```bash
git clone https://github.com/kalpakjian/Digital-Clock.git
```

下載完成後，進入專案資料夾：

```bash
cd Digital-Clock
```

## 如何用 Unity Hub 開啟專案

1. 先安裝 **Unity Hub**。
2. 確認 Unity Hub 內已安裝 **Unity 2022.3.62f3**（含 URP 支援）。
3. 使用 `git clone` 下載此專案到本機。
4. 開啟 **Unity Hub**。
5. 在左側選擇 **Projects**。
6. 點擊右上角 **Open** 或 **Add project from disk**。
7. 選擇剛剛 `git clone` 下來的 `Digital-Clock` 專案資料夾。
8. Unity Hub 會偵測此專案，確認編輯器版本為 **2022.3.62f1** 後開啟。
9. 第一次開啟時，Unity 可能需要一些時間匯入專案檔案。
10. 開啟後，在 **Assets** 資料夾中找到 `DigitalTimer.unity`，雙擊開啟場景，按 Play 即可執行。

## 注意事項

- 如果 Unity Hub 顯示缺少對應版本，請先安裝 **Unity 2022.3.62f3** 再開啟專案。
- 若開啟後出現套件重新匯入或編譯時間較長，屬於正常情況。
- 建議使用與專案相同的 Unity 版本，以避免設定或相容性問題。
- Visual Scripting 圖儲存於 `Assets/digitalClock.asset`，可在 Unity Editor 中以 Visual Scripting 視窗開啟查看邏輯。

## 適合練習的主題

你可以用這個專案進一步練習：

- 修改計數上限（目前為 999），例如改為 59 模擬秒數顯示
- 將三個 digit 改為顯示真實系統時鐘（`System.DateTime.Now`）
- 加入歸零按鈕，透過 Visual Scripting 的 `On Button Click` 事件重設計數
- 將數字材質換成自訂顏色或發光材質，增加視覺效果
- 將 Visual Scripting 邏輯改寫成 C# 腳本，練習程式碼版本的實作
- 加入音效，每次進位時播放提示音

## 作者

Mike Lau

## Repository

GitHub: <https://github.com/kalpakjian/Digital-Clock>
