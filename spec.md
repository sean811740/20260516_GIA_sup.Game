# 橫向卷軸遊戲專案規格書：暗影之境 (Shadow's Realm)

這是一份針對類「空洞騎士 (Hollow Knight)」風格的網頁橫向卷軸射擊遊戲的開發規格書。

## 1. 遊戲概述
*   **遊戲類型**：2D 橫向卷軸動作射擊遊戲 (Side-scroller Action Shooter)。
*   **運行平台**：網頁瀏覽器 (Chrome, Firefox, Edge, Safari)。
*   **核心玩法**：玩家操控角色在平台間移動跳躍，並利用定時發射的子彈擊敗迎面而來的敵人，探索深邃的地下世界。

## 2. 視覺與氛圍 (Visual & Aesthetic)
![遊戲風格參考概念圖](C:/Users/sean1/.gemini/antigravity/brain/2a6f9044-8439-432e-a412-a151d7a912bd/hollow_knight_style_game_concept_1778910798258.png)

*   **美術風格**：深沉、憂鬱且具有手繪質感的暗色調風格。
*   **環境效果**：
    *   多層捲軸背景 (Parallax Scrolling) 增加深度感。
    *   動態粒子效果（如發光的孢子、塵埃）。
    *   角色的子彈與敵人的死亡伴隨微弱的光效 (Glow Effect)。
*   **色彩方案**：以深藍、深紫、灰色為主色調，配合亮色的子彈與敵人特徵作為視覺指引。

## 3. 核心機制 (Core Mechanics)
### 3.1 角色控制 (Player Controller)
*   **移動**：左右平移（具有加速度與摩擦力，使操作感流暢）。
*   **跳躍**：具有重力感應的跳躍與二段跳（可選）。
*   **射擊機制**：
    *   **自動/定時射擊**：玩家不需要瘋狂點擊，角色會每隔固定時間（如 0.5 秒）自動向前方發射子彈。
    *   **子彈特性**：直線水平飛行，碰到敵人或牆壁消失。

### 3.2 敵人系統 (Enemy System)
*   **巡邏敵**：在固定平台範圍內往返移動。
*   **飛行敵**：追蹤玩家位置或呈波浪狀飛行。
*   **血量系統**：敵人被子彈擊中一定次數後消失，並產生小規模爆炸特效。

### 3.3 關卡設計 (Level Design)
*   **攝影機控制**：平滑跟隨玩家 (Smooth Follow)。
*   **碰撞系統**：角色與牆壁、地面、天花板的精確碰撞檢測。
*   **存檔點系統**：在地圖中設置特定地點（如長椅或石碑），玩家觸碰後即更新重生點。玩家死亡後將在最後一個存檔點復活。

## 4. 技術架構 (Technical Stack)
*   **核心語言**：JavaScript (ES6+)。
*   **渲染技術**：HTML5 Canvas API (高效繪製大量粒子與精靈圖)。
*   **狀態管理**：自定義遊戲引擎循環 (Game Loop)，使用 `requestAnimationFrame`。
*   **資源管理**：非同步載入圖片與音效。

## 5. 檔案結構建議
```text
/src
  /assets        # 圖片、音效資源
  /core          # 遊戲引擎核心 (GameLoop, InputHandler)
  /entities      # 遊戲物件 (Player, Enemy, Bullet)
  /world         # 地圖與碰撞邏輯
  main.js        # 進入點
index.html       # 網頁結構
style.css        # 樣式與排版
```

## 6. 開發里程碑 (Milestones)
1.  **Phase 1: 原型開發** - 實現角色基本移動與重力系統。
2.  **Phase 2: 戰鬥基礎** - 實現子彈定時發射與碰撞判定。
3.  **Phase 4: 視覺強化** - 加入背景層次感、光影與轉場動畫。
4.  **Phase 5: 音效與打磨** - 加入戰鬥音效與背景音樂，進行效能優化。

---

## 視覺資源參考 (Visual Resources)
以下為您生成的基礎視覺風格參考：

### 1. 整體場景概念
![遊戲風格參考概念圖](C:/Users/sean1/.gemini/antigravity/brain/2a6f9044-8439-432e-a412-a151d7a912bd/hollow_knight_style_game_concept_1778910798258.png)

### 2. 角色設計參考 (主角)
![角色設計參考](C:/Users/sean1/.gemini/antigravity/brain/2a6f9044-8439-432e-a412-a151d7a912bd/hollow_knight_character_reference_1778910989300.png)
