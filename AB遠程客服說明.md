 ```html
<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AB 錢包遠程客服 - Long Hoang 崗位管理規範</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Microsoft JhengHei', 'Segoe UI', sans-serif;
            background: linear-gradient(135deg, #1a1a2e 0%, #16213e 50%, #0f3460 100%);
            min-height: 100vh;
            padding: 20px;
            color: #eaeaea;
        }
        
        .container {
            max-width: 1400px;
            margin: 0 auto;
        }
        
        .header {
            text-align: center;
            margin-bottom: 30px;
            padding: 25px;
            background: rgba(255,255,255,0.05);
            border-radius: 20px;
            border: 1px solid rgba(255,255,255,0.1);
            backdrop-filter: blur(10px);
        }
        
        .header h1 {
            font-size: 2.5em;
            margin-bottom: 10px;
            background: linear-gradient(45deg, #ffd700, #ffed4e);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-shadow: 0 0 30px rgba(255,215,0,0.3);
        }
        
        .header .subtitle {
            color: #a0a0a0;
            font-size: 1.1em;
            margin-top: 10px;
        }
        
        .header .subtitle a {
            color: #ffd700;
            text-decoration: none;
            border-bottom: 1px solid rgba(255,215,0,0.5);
            transition: all 0.3s ease;
        }
        
        .header .subtitle a:hover {
            color: #fff;
            border-bottom-color: #fff;
            text-shadow: 0 0 10px rgba(255,215,0,0.5);
        }
        
        .grid-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
            gap: 20px;
            margin-bottom: 20px;
        }
        
        .card {
            background: rgba(255,255,255,0.05);
            border-radius: 15px;
            padding: 20px;
            border: 1px solid rgba(255,255,255,0.1);
            backdrop-filter: blur(10px);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        
        .card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(0,0,0,0.3);
            border-color: rgba(255,215,0,0.3);
        }
        
        .card-title {
            font-size: 1.3em;
            margin-bottom: 15px;
            padding-bottom: 10px;
            border-bottom: 2px solid rgba(255,215,0,0.5);
            color: #ffd700;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .card-title::before {
            content: '▸';
            color: #ffd700;
        }
        
        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 10px;
            font-size: 0.95em;
        }
        
        th, td {
            padding: 12px;
            text-align: left;
            border-bottom: 1px solid rgba(255,255,255,0.1);
        }
        
        th {
            background: rgba(255,215,0,0.1);
            color: #ffd700;
            font-weight: 600;
        }
        
        tr:hover {
            background: rgba(255,255,255,0.03);
        }
        
        .highlight {
            color: #ffd700;
            font-weight: bold;
        }
        
        .highlight-red {
            color: #e74c3c;
            font-weight: bold;
        }
        
        .highlight-green {
            color: #2ecc71;
            font-weight: bold;
        }
        
        .list-item {
            padding: 8px 0;
            padding-left: 20px;
            position: relative;
            line-height: 1.6;
        }
        
        .list-item::before {
            content: '•';
            position: absolute;
            left: 0;
            color: #ffd700;
        }
        
        .full-width {
            grid-column: 1 / -1;
        }
        
        .shift-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 10px;
            margin-top: 10px;
        }
        
        .shift-card {
            background: rgba(255,255,255,0.03);
            padding: 15px;
            border-radius: 10px;
            text-align: center;
            border: 1px solid rgba(255,255,255,0.05);
        }
        
        .shift-card h4 {
            color: #ffd700;
            margin-bottom: 10px;
            font-size: 1.1em;
        }
        
        .time-display {
            font-size: 1.2em;
            font-weight: bold;
            color: #fff;
            margin: 5px 0;
        }
        
        .badge {
            display: inline-block;
            padding: 3px 10px;
            border-radius: 12px;
            font-size: 0.85em;
            font-weight: bold;
            margin-left: 10px;
        }
        
        .badge-warning {
            background: rgba(231, 76, 60, 0.3);
            color: #e74c3c;
        }
        
        .badge-info {
            background: rgba(52, 152, 219, 0.3);
            color: #3498db;
        }
        
        .footer-status {
            background: rgba(0,0,0,0.3);
            padding: 15px;
            border-radius: 10px;
            margin-top: 20px;
            text-align: center;
            font-size: 0.9em;
            color: #888;
            border: 1px solid rgba(255,255,255,0.05);
        }
        
        .icon {
            font-size: 1.2em;
            margin-right: 5px;
        }
        
        @media (max-width: 768px) {
            .grid-container {
                grid-template-columns: 1fr;
            }
            .shift-grid {
                grid-template-columns: 1fr;
            }
            .header h1 {
                font-size: 1.8em;
            }
        }
        
        .checklist {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 10px;
        }
        
        .check-item {
            background: rgba(255,255,255,0.03);
            padding: 10px;
            border-radius: 8px;
            border-left: 3px solid #2ecc71;
        }
        
        .notice-box {
            background: rgba(255, 215, 0, 0.1);
            border: 1px solid rgba(255, 215, 0, 0.3);
            border-radius: 10px;
            padding: 15px;
            margin-top: 15px;
            font-size: 0.9em;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>👑 AB 錢包遠程客服</h1>
            <div class="subtitle">
                <a href="https://www.facebook.com/hoanglongcameo" target="_blank">Long Hoang</a> 
                崗位管理規範系統
            </div>
        </div>
        
        <div class="grid-container">
            <!-- 薪資結構 -->
            <div class="card">
                <div class="card-title">💰 薪資結構</div>
                <table>
                    <tr>
                        <th>階段</th>
                        <th>底薪</th>
                        <th>績效</th>
                        <th>合計</th>
                    </tr>
                    <tr>
                        <td>試用期 <span class="badge badge-warning">1個月</span></td>
                        <td class="highlight">850U</td>
                        <td>150U</td>
                        <td>1000U</td>
                    </tr>
                    <tr>
                        <td>轉正後</td>
                        <td class="highlight">1000U</td>
                        <td class="highlight">300U</td>
                        <td class="highlight-green">1300U</td>
                    </tr>
                    <tr>
                        <td>滿半年 <span class="badge badge-info">+100U</span></td>
                        <td>1100U</td>
                        <td>300U</td>
                        <td>1400U</td>
                    </tr>
                    <tr>
                        <td>滿一年 <span class="badge badge-info">+100U</span></td>
                        <td>1200U</td>
                        <td>300U</td>
                        <td>1500U</td>
                    </tr>
                </table>
                <div class="notice-box">
                    <strong>🎁 年假福利：</strong>滿一年享15天年假，<span class="highlight">不休可領750U補貼</span>
                </div>
            </div>
            
            <!-- 押金制度 -->
            <div class="card">
                <div class="card-title">🔒 押金制度</div>
                <table>
                    <tr>
                        <th>項目</th>
                        <th>詳情</th>
                    </tr>
                    <tr>
                        <td>押金金額</td>
                        <td class="highlight">400U</td>
                    </tr>
                    <tr>
                        <td>扣除方式</td>
                        <td>每月扣100U，分4個月扣完</td>
                    </tr>
                    <tr>
                        <td>退還條件</td>
                        <td class="highlight-green">滿一年 或 提前2個月申請離職</td>
                    </tr>
                    <tr>
                        <td>不退還情形</td>
                        <td class="highlight-red">一年內離職（未提前2個月申請）</td>
                    </tr>
                </table>
                <div class="notice-box" style="border-color: #e74c3c; background: rgba(231, 76, 60, 0.1);">
                    <strong>⚠️ 注意：</strong>離職時才可領取押金，請妥善規劃職涯
                </div>
            </div>
            
            <!-- 上班時間 -->
            <div class="card">
                <div class="card-title">⏰ 上班時間安排</div>
                <table>
                    <tr>
                        <th>項目</th>
                        <th>說明</th>
                    </tr>
                    <tr>
                        <td>每日工時</td>
                        <td class="highlight">12小時</td>
                    </tr>
                    <tr>
                        <td>換班週期</td>
                        <td>每月月底換班一次</td>
                    </tr>
                    <tr>
                        <td>換班當天</td>
                        <td class="highlight-red">工作18小時（交接）</td>
                    </tr>
                    <tr>
                        <td>用餐時間</td>
                        <td>每班2次，每次30分鐘</td>
                    </tr>
                    <tr>
                        <td>發薪日</td>
                        <td class="highlight-green">每月15號</td>
                    </tr>
                    <tr>
                        <td>月休</td>
                        <td>2天</td>
                    </tr>
                </table>
            </div>
            
            <!-- 班次表 -->
            <div class="card full-width">
                <div class="card-title">📅 班次時間表（北京時間）</div>
                <div class="shift-grid">
                    <div class="shift-card">
                        <h4>🌅 班次一</h4>
                        <div class="time-display">08:00 – 20:00</div>
                        <div style="color: #888; margin: 5px 0;">⬇️ 換班 ⬇️</div>
                        <div class="time-display" style="color: #a0a0ff;">20:00 – 08:00</div>
                    </div>
                    <div class="shift-card">
                        <h4>🌞 班次二</h4>
                        <div class="time-display">09:00 – 21:00</div>
                        <div style="color: #888; margin: 5px 0;">⬇️ 換班 ⬇️</div>
                        <div class="time-display" style="color: #a0a0ff;">21:00 – 09:00</div>
                    </div>
                    <div class="shift-card">
                        <h4>🌆 班次三</h4>
                        <div class="time-display">10:00 – 22:00</div>
                        <div style="color: #888; margin: 5px 0;">⬇️ 換班 ⬇️</div>
                        <div class="time-display" style="color: #a0a0ff;">22:00 – 10:00</div>
                    </div>
                </div>
                <div class="notice-box" style="margin-top: 15px;">
                    <strong>📢 重要提醒：</strong>具體班次由現場負責人統一安排，<span class="highlight-red">不得私自調整</span>
                </div>
            </div>
            
            <!-- 上崗準備 -->
            <div class="card">
                <div class="card-title">🖥️ 上崗前準備</div>
                <div class="checklist">
                    <div class="check-item">
                        <strong>1.</strong> 配備穩定可用的電腦設備
                    </div>
                    <div class="check-item">
                        <strong>2.</strong> 安裝並測試網絡環境
                    </div>
                    <div class="check-item">
                        <strong>3.</strong> 安裝工作所需軟件<br>
                        <small style="color: #888;">（飛機、谷歌瀏覽器、ABpay郵箱、VPN固定線路）</small>
                    </div>
                    <div class="check-item">
                        <strong>4.</strong> 安裝Zoom軟件<br>
                        <span class="highlight-red">（需安裝攝像頭）</span>
                    </div>
                </div>
                <div class="notice-box">
                    確保設備、網絡穩定，滿足長期在線客服需求
                </div>
            </div>
            
            <!-- 學習要求 -->
            <div class="card">
                <div class="card-title">📚 上崗前學習要求</div>
                <div class="list-item">熟悉公司產品及業務流程</div>
                <div class="list-item">熟練掌握錢包 APP / H5 的下載與操作</div>
                <div class="list-item">學習並掌握常見問題的標準處理步驟</div>
                <div class="notice-box" style="border-color: #2ecc71;">
                    <strong>💡 提醒：</strong>上崗初期需保持持續學習，不懂及時諮詢溝通，避免盲目處理
                </div>
            </div>
            
            <!-- 績效考核 -->
            <div class="card">
                <div class="card-title">📊 績效考核內容</div>
                <table>
                    <tr>
                        <th>考核項目</th>
                        <th>說明</th>
                    </tr>
                    <tr>
                        <td>日常考勤</td>
                        <td>紀律執行情況</td>
                    </tr>
                    <tr>
                        <td>學習進度</td>
                        <td>問題掌握情況</td>
                    </tr>
                    <tr>
                        <td>服務質量</td>
                        <td>回覆及時性與服務態度</td>
                    </tr>
                    <tr>
                        <td>工作配合</td>
                        <td>工作狀態與配合度</td>
                    </tr>
                </table>
                <div style="margin-top: 10px; font-size: 0.9em; color: #888;">
                    績效記錄由對應的現場負責人根據實際出勤與工作表現進行統計
                </div>
            </div>
            
            <!-- 試崗轉正 -->
            <div class="card">
                <div class="card-title">🎯 試崗與轉正</div>
                <table>
                    <tr>
                        <th>項目</th>
                        <th>內容</th>
                    </tr>
                    <tr>
                        <td>試崗週期</td>
                        <td>1週內需熟練掌握常見基礎問題處理</td>
                    </tr>
                    <tr>
                        <td>轉正週期</td>
                        <td class="highlight">1個月</td>
                    </tr>
                    <tr>
                        <td>考核依據</td>
                        <td>學習情況、工作表現、綜合評估</td>
                    </tr>
                </table>
                <div class="notice-box">
                    試崗期間保持持續學習，不懂的問題主動提問，現場負責人將進行培訓、輔導及階段性考核
                </div>
            </div>
            
            <!-- 工作要求 -->
            <div class="card full-width">
                <div class="card-title">💼 在線客服工作要求</div>
                <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 15px;">
                    <div class="check-item" style="border-left-color: #3498db;">
                        <strong>1.</strong> 在線期間需及時回覆會員消息
                    </div>
                    <div class="check-item" style="border-left-color: #e74c3c;">
                        <strong>2.</strong> 遇到不確定的問題，需第一時間在群內諮詢處理
                    </div>
                    <div class="check-item" style="border-left-color: #9b59b6;">
                        <strong>3.</strong> 工作群、小組群、總群消息必須及時查看<br>
                        <small style="color: #ffd700;">【工作互相配合】</small>
                    </div>
                    <div class="check-item" style="border-left-color: #e67e22;">
                        <strong>4.</strong> 群內通知與工作要求需嚴格執行，<span class="highlight-red">不得忽視</span>
                    </div>
                </div>
            </div>
            
            <!-- 工作態度 -->
            <div class="card full-width">
                <div class="card-title">🌟 基本工作態度要求</div>
                <div style="display: flex; justify-content: space-around; flex-wrap: wrap; gap: 20px; padding: 20px 0;">
                    <div style="text-align: center; padding: 20px; background: rgba(255,255,255,0.03); border-radius: 10px; min-width: 150px;">
                        <div style="font-size: 2em; margin-bottom: 10px;">✅</div>
                        <div>積極學習<br>主動溝通</div>
                    </div>
                    <div style="text-align: center; padding: 20px; background: rgba(255,255,255,0.03); border-radius: 10px; min-width: 150px;">
                        <div style="font-size: 2em; margin-bottom: 10px;">✅</div>
                        <div>認真對待<br>每一位會員</div>
                    </div>
                    <div style="text-align: center; padding: 20px; background: rgba(255,255,255,0.03); border-radius: 10px; min-width: 150px;">
                        <div style="font-size: 2em; margin-bottom: 10px;">✅</div>
                        <div>嚴格執行流程<br>服從管理安排</div>
                    </div>
                </div>
                <div class="notice-box" style="text-align: center; font-size: 1.1em;">
                    💡 客服是公司與會員之間的重要窗口，<span class="highlight">服務質量直接影響平台形象</span>
                </div>
            </div>
        </div>
        
        <div class="footer-status">
            <strong>▫️ 紀錄目前開機時間</strong> <span style="color: #ffd700; font-family: monospace;">***</span> / 月<br>
            <small>系統版本 v1.0 | 最後更新：2026-03-01</small>
        </div>
    </div>
</body>
</html>
```
