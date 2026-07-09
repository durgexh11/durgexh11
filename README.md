<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>LeetCode Profile - Durgesh</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            background: #0d1117;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
            padding: 20px;
        }
        .container {
            max-width: 900px;
            width: 100%;
            background: #161b22;
            border-radius: 16px;
            border: 1px solid #30363d;
            padding: 32px 28px;
            color: #c9d1d9;
        }

        /* Header */
        .profile-header {
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
            margin-bottom: 24px;
            flex-wrap: wrap;
        }
        .profile-left {
            display: flex;
            gap: 16px;
            align-items: center;
        }
        .avatar {
            width: 72px;
            height: 72px;
            border-radius: 50%;
            background: #30363d;
            border: 2px solid #ffa116;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 32px;
            font-weight: 600;
            color: #ffa116;
        }
        .profile-info h1 {
            font-size: 24px;
            font-weight: 700;
            color: #f0f6fc;
            margin-bottom: 2px;
        }
        .profile-info .username {
            color: #8b949e;
            font-size: 14px;
            margin-bottom: 4px;
        }
        .rank-badge {
            background: #1c2333;
            padding: 2px 12px;
            border-radius: 12px;
            font-size: 13px;
            color: #ffa116;
            border: 1px solid #30363d;
            display: inline-block;
        }
        .follow-stats {
            display: flex;
            gap: 16px;
            font-size: 14px;
            color: #8b949e;
            margin-top: 4px;
        }
        .follow-stats span strong {
            color: #f0f6fc;
            font-weight: 600;
        }
        .profile-right {
            text-align: right;
        }
        .edit-btn {
            background: transparent;
            border: 1px solid #30363d;
            color: #c9d1d9;
            padding: 4px 16px;
            border-radius: 20px;
            font-size: 13px;
            cursor: pointer;
            transition: 0.2s;
        }
        .edit-btn:hover {
            background: #30363d;
        }
        .location {
            font-size: 14px;
            color: #8b949e;
            margin-top: 6px;
        }
        .social-links {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            margin-top: 6px;
            justify-content: flex-end;
            font-size: 13px;
            color: #58a6ff;
        }
        .social-links span {
            color: #8b949e;
        }

        /* Tags */
        .tags {
            display: flex;
            gap: 6px;
            flex-wrap: wrap;
            margin: 12px 0 18px;
        }
        .tag {
            background: #1c2333;
            border: 1px solid #30363d;
            padding: 2px 12px;
            border-radius: 12px;
            font-size: 12px;
            color: #8b949e;
        }

        /* Community Stats */
        .community-stats {
            display: flex;
            gap: 24px;
            flex-wrap: wrap;
            background: #0d1117;
            border-radius: 10px;
            padding: 14px 18px;
            margin-bottom: 20px;
            border: 1px solid #30363d;
        }
        .stat-item {
            display: flex;
            flex-direction: column;
        }
        .stat-item .label {
            font-size: 11px;
            color: #8b949e;
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }
        .stat-item .value {
            font-size: 16px;
            font-weight: 600;
            color: #f0f6fc;
        }
        .stat-item .sub {
            font-size: 11px;
            color: #8b949e;
        }

        /* Languages */
        .section-title {
            font-size: 15px;
            font-weight: 600;
            color: #f0f6fc;
            margin-bottom: 10px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        .section-title a {
            color: #58a6ff;
            font-size: 13px;
            font-weight: 400;
            text-decoration: none;
        }
        .language-item {
            display: flex;
            justify-content: space-between;
            padding: 6px 0;
            border-bottom: 1px solid #21262d;
            font-size: 14px;
        }
        .language-item:last-child {
            border-bottom: none;
        }
        .lang-name {
            color: #f0f6fc;
        }
        .lang-solved {
            color: #8b949e;
        }

        /* Skills */
        .skills-grid {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            margin-top: 6px;
        }
        .skill-item {
            background: #1c2333;
            border: 1px solid #30363d;
            padding: 4px 14px;
            border-radius: 12px;
            font-size: 13px;
            color: #c9d1d9;
            display: flex;
            align-items: center;
            gap: 4px;
        }
        .skill-item .emoji {
            font-size: 14px;
        }

        /* Contest Rating */
        .contest-card {
            background: #0d1117;
            border: 1px solid #30363d;
            border-radius: 10px;
            padding: 16px 18px;
            margin: 20px 0;
        }
        .contest-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
        }
        .contest-rating {
            font-size: 28px;
            font-weight: 700;
            color: #ffa116;
        }
        .contest-rank {
            font-size: 14px;
            color: #8b949e;
        }
        .contest-rank strong {
            color: #f0f6fc;
        }
        .contest-percent {
            color: #3fb950;
            font-weight: 600;
        }
        .contest-dates {
            display: flex;
            gap: 12px;
            font-size: 13px;
            color: #8b949e;
        }
        .contest-dates span {
            background: #1c2333;
            padding: 2px 10px;
            border-radius: 12px;
            border: 1px solid #30363d;
        }
        .solved-stats {
            display: flex;
            gap: 24px;
            margin-top: 12px;
            flex-wrap: wrap;
        }
        .solved-number {
            font-size: 22px;
            font-weight: 700;
            color: #f0f6fc;
        }
        .solved-label {
            font-size: 12px;
            color: #8b949e;
        }
        .difficulty-easy {
            color: #00b8a3;
        }
        .difficulty-hard {
            color: #ef4743;
        }
        .badge-item {
            display: inline-block;
            background: #1c2333;
            border: 1px solid #30363d;
            padding: 2px 12px;
            border-radius: 12px;
            font-size: 12px;
            color: #ffa116;
            margin-top: 6px;
        }

        /* Heatmap */
        .heatmap-section {
            margin: 20px 0;
        }
        .heatmap-stats {
            display: flex;
            gap: 24px;
            font-size: 13px;
            color: #8b949e;
            flex-wrap: wrap;
        }
        .heatmap-stats strong {
            color: #f0f6fc;
        }

        /* Problems List */
        .problems-list {
            margin-top: 14px;
        }
        .problem-item {
            display: flex;
            justify-content: space-between;
            padding: 8px 0;
            border-bottom: 1px solid #21262d;
            font-size: 14px;
        }
        .problem-item:last-child {
            border-bottom: none;
        }
        .problem-name {
            color: #58a6ff;
            text-decoration: none;
        }
        .problem-name:hover {
            text-decoration: underline;
        }
        .problem-difficulty {
            font-size: 12px;
            padding: 2px 10px;
            border-radius: 12px;
            background: #1c2333;
            border: 1px solid #30363d;
        }
        .difficulty-easy-tag {
            color: #00b8a3;
        }
        .difficulty-medium-tag {
            color: #d29922;
        }
        .difficulty-hard-tag {
            color: #ef4743;
        }

        .view-all {
            color: #58a6ff;
            text-decoration: none;
            font-size: 14px;
            display: inline-block;
            margin-top: 6px;
        }

        /* Comment box */
        .comment-box {
            margin-top: 18px;
            background: #0d1117;
            border: 1px solid #30363d;
            border-radius: 10px;
            padding: 12px 16px;
            color: #8b949e;
            font-size: 14px;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        .comment-box .avatar-small {
            width: 28px;
            height: 28px;
            border-radius: 50%;
            background: #30363d;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 12px;
            font-weight: 600;
            color: #ffa116;
            flex-shrink: 0;
        }

        /* Responsive */
        @media (max-width: 600px) {
            .profile-header {
                flex-direction: column;
                align-items: flex-start;
                gap: 12px;
            }
            .profile-right {
                text-align: left;
                width: 100%;
            }
            .social-links {
                justify-content: flex-start;
            }
            .community-stats {
                gap: 12px;
            }
            .contest-header {
                flex-direction: column;
                align-items: flex-start;
                gap: 6px;
            }
        }
    </style>
</head>
<body>

<div class="container">

    <!-- ====== PROFILE HEADER ====== -->
    <div class="profile-header">
        <div class="profile-left">
            <div class="avatar">D</div>
            <div class="profile-info">
                <h1>Durgesh</h1>
                <div class="username">@durgexh11</div>
                <div>
                    <span class="rank-badge">Rank 379,047</span>
                </div>
                <div class="follow-stats">
                    <span><strong>7</strong> Following</span>
                    <span><strong>10</strong> Followers</span>
                </div>
            </div>
        </div>
        <div class="profile-right">
            <button class="edit-btn">Edit Profile</button>
            <div class="location">India</div>
            <div class="social-links">
                <span>https://portfolio.durgesh.dev/</span>
                <span>durgexh11</span>
                <span>X 40k+_durgesh</span>
                <span>in durgexh11</span>
            </div>
        </div>
    </div>

    <!-- Tags -->
    <div class="tags">
        <span class="tag">Full Stack</span>
        <span class="tag">Backend</span>
        <span class="tag">Frontend</span>
    </div>

    <!-- ====== COMMUNITY STATS ====== -->
    <div class="community-stats">
        <div class="stat-item">
            <span class="label">Views</span>
            <span class="value">223</span>
            <span class="sub">Last week</span>
        </div>
        <div class="stat-item">
            <span class="label">Solution</span>
            <span class="value">0</span>
            <span class="sub">Last week</span>
        </div>
        <div class="stat-item">
            <span class="label">Discussion</span>
            <span class="value">2</span>
            <span class="sub">Last week</span>
        </div>
        <div class="stat-item">
            <span class="label">Reputation</span>
            <span class="value">7</span>
            <span class="sub">Last week</span>
        </div>
    </div>

    <!-- ====== LANGUAGES ====== -->
    <div class="section-title">
        <span>Languages</span>
        <a href="#">Show more</a>
    </div>
    <div class="language-item">
        <span class="lang-name">C++</span>
        <span class="lang-solved">244 problems solved</span>
    </div>
    <div class="language-item">
        <span class="lang-name">Java</span>
        <span class="lang-solved">117 problems solved</span>
    </div>
    <div class="language-item">
        <span class="lang-name">JavaScript</span>
        <span class="lang-solved">16 problems solved</span>
    </div>

    <!-- ====== SKILLS ====== -->
    <div class="section-title" style="margin-top:18px;">
        <span>Skills</span>
        <a href="#">Show more</a>
    </div>
    <div class="skills-grid">
        <span class="skill-item"><span class="emoji">📊</span> Dynamic Programming</span>
        <span class="skill-item"><span class="emoji">📊</span> Child and Computer</span>
        <span class="skill-item"><span class="emoji">📊</span> Backtracking</span>
    </div>

    <!-- ====== CONTEST RATING ====== -->
    <div class="contest-card">
        <div class="contest-header">
            <div>
                <span style="font-size:14px;color:#8b949e;">Contest Rating</span>
                <div class="contest-rating">1,681</div>
            </div>
            <div style="text-align:right;">
                <div class="contest-rank">Global Ranking <strong>138,672</strong> (74,830)</div>
                <div class="contest-percent">Top 15.21%</div>
                <div class="contest-dates">
                    <span>Mar 2026</span>
                    <span>May 2026</span>
                </div>
            </div>
        </div>

        <div class="solved-stats">
            <div>
                <div class="solved-number">349</div>
                <div class="solved-label">Solved</div>
            </div>
            <div>
                <div class="solved-number">9</div>
                <div class="solved-label">Attempting</div>
            </div>
            <div>
                <div class="solved-number" style="color:#00b8a3;">172,961</div>
                <div class="solved-label">Easy</div>
            </div>
            <div>
                <div class="solved-number" style="color:#ef4743;">30,048</div>
                <div class="solved-label">Hard</div>
            </div>
            <div>
                <div class="solved-number" style="font-size:16px;color:#ffa116;">Best Recent Rating</div>
                <div class="badge-item">100 Days Badge 2026</div>
            </div>
        </div>
    </div>

    <!-- ====== HEATMAP ====== -->
    <div class="heatmap-section">
        <div style="background:#0d1117;border:1px solid #30363d;border-radius:10px;padding:16px 18px;">
            <div style="display:flex;justify-content:space-between;flex-wrap:wrap;gap:8px;">
                <span style="font-size:14px;color:#f0f6fc;font-weight:500;">620 submissions in the past one year</span>
                <div class="heatmap-stats">
                    <span>Total active days: <strong>223</strong></span>
                    <span>Max streak: <strong>128</strong></span>
                </div>
            </div>
            <!-- Heatmap placeholder (would be an image in real LeetCode) -->
            <div style="margin-top:12px;background:#1c2333;border-radius:6px;height:60px;display:flex;align-items:center;justify-content:center;color:#8b949e;font-size:13px;border:1px solid #30363d;">
                🟩🟩🟨🟩⬜🟩🟨🟩⬜🟩🟩🟨🟩⬜🟩🟨🟩⬜🟩🟩🟨🟩⬜🟩🟨🟩⬜
            </div>
        </div>
    </div>

    <!-- ====== PROBLEMS LIST ====== -->
    <div class="section-title">
        <span>Recent Problems</span>
        <a href="#">View all submissions</a>
    </div>
    <div class="problems-list">
        <div class="problem-item">
            <a href="#" class="problem-name">Rotting Oranges</a>
            <span class="problem-difficulty difficulty-medium-tag">Medium</span>
        </div>
        <div class="problem-item">
            <a href="#" class="problem-name">Find the Safest Path in a Grid</a>
            <span class="problem-difficulty difficulty-hard-tag">Hard</span>
        </div>
        <div class="problem-item">
            <a href="#" class="problem-name">Number of Substrings Containing All Three Characters</a>
            <span class="problem-difficulty difficulty-medium-tag">Medium</span>
        </div>
        <div class="problem-item">
            <a href="#" class="problem-name">Number of Strings That Appear as Substrings in Word</a>
            <span class="problem-difficulty difficulty-easy-tag">Easy</span>
        </div>
        <div class="problem-item">
            <a href="#" class="problem-name">Maximum Element After Decreasing and Rearranging</a>
            <span class="problem-difficulty difficulty-medium-tag">Medium</span>
        </div>
        <div class="problem-item">
            <a href="#" class="problem-name">Find the Maximum Number of Elements in Subset</a>
            <span class="problem-difficulty difficulty-medium-tag">Medium</span>
        </div>
        <div class="problem-item">
            <a href="#" class="problem-name">Count Subarrays With Majority Element</a>
            <span class="problem-difficulty difficulty-hard-tag">Hard</span>
        </div>
        <div class="problem-item">
            <a href="#" class="problem-name">Find a Safe Walk Through a Grid</a>
            <span class="problem-difficulty difficulty-medium-tag">Medium</span>
        </div>
    </div>

    <!-- ====== COMMENT BOX ====== -->
    <div class="comment-box">
        <div class="avatar-small">D</div>
        <span>Add comment...</span>
    </div>

</div>

</body>
</html>
