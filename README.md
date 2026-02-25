<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>مدرسه کار و دانش شهید عظیمی | قزوین</title>
    <link href="https://fonts.googleapis.com/css2?family=Vazirmatn:wght@300;400;500;600;700;800;900&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary: #6366f1;
            --primary-dark: #4f46e5;
            --secondary: #8b5cf6;
            --accent: #f59e0b;
            --success: #10b981;
            --danger: #ef4444;
            --dark: #0f172a;
            --light: #f8fafc;
            --bg: #f1f5f9;
            --card: #ffffff;
            --text: #1e293b;
            --text-muted: #64748b;
            --glass: rgba(255, 255, 255, 0.7);
        }

        [data-theme="dark"] {
            --bg: #0f172a;
            --card: #1e293b;
            --text: #f8fafc;
            --text-muted: #94a3b8;
            --dark: #f8fafc;
            --light: #334155;
            --glass: rgba(30, 41, 59, 0.7);
        }

        body {
            font-family: 'Vazirmatn', Tahoma, Arial, sans-serif;
            background: var(--bg);
            color: var(--text);
            line-height: 1.6;
            direction: rtl;
            transition: all 0.3s ease;
            overflow-x: hidden;
        }

        /* Animated Background */
        .bg-animation {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            overflow: hidden;
        }

        .bg-animation::before {
            content: '';
            position: absolute;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.1) 1px, transparent 1px);
            background-size: 50px 50px;
            animation: moveGrid 20s linear infinite;
        }

        @keyframes moveGrid {
            0% { transform: translate(0, 0); }
            100% { transform: translate(50px, 50px); }
        }

        /* Loading Screen */
        .loader {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            z-index: 99999;
            transition: opacity 0.5s;
        }

        .loader.hidden {
            opacity: 0;
            pointer-events: none;
        }

        .loader-logo {
            width: 150px;
            height: 150px;
            background: rgba(255,255,255,0.2);
            backdrop-filter: blur(10px);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 80px;
            margin-bottom: 30px;
            animation: float 3s ease-in-out infinite;
            box-shadow: 0 20px 60px rgba(0,0,0,0.3);
            border: 2px solid rgba(255,255,255,0.3);
        }

        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
        }

        .loader-text {
            color: white;
            font-size: 28px;
            font-weight: 800;
            text-shadow: 0 2px 10px rgba(0,0,0,0.2);
        }

        .loader-subtext {
            color: rgba(255,255,255,0.8);
            margin-top: 10px;
            font-size: 16px;
        }

        /* Header */
        header {
            background: var(--glass);
            backdrop-filter: blur(20px);
            box-shadow: 0 4px 30px rgba(0,0,0,0.1);
            position: sticky;
            top: 0;
            z-index: 1000;
            border-bottom: 1px solid rgba(255,255,255,0.2);
        }

        .top-bar {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 12px 0;
            font-size: 14px;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        .top-bar-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 10px;
        }

        .contact-info span {
            margin-left: 20px;
            display: inline-flex;
            align-items: center;
            gap: 5px;
        }

        .header-actions {
            display: flex;
            gap: 15px;
            align-items: center;
        }

        .theme-toggle {
            background: rgba(255,255,255,0.2);
            border: none;
            color: white;
            padding: 8px 20px;
            border-radius: 25px;
            cursor: pointer;
            font-family: inherit;
            transition: all 0.3s;
            backdrop-filter: blur(10px);
        }

        .theme-toggle:hover {
            background: rgba(255,255,255,0.3);
            transform: scale(1.05);
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 0;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .logo-icon {
            width: 60px;
            height: 60px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            border-radius: 16px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 32px;
            color: white;
            box-shadow: 0 10px 30px rgba(102, 126, 234, 0.4);
            animation: glow 3s ease-in-out infinite;
        }

        @keyframes glow {
            0%, 100% { box-shadow: 0 10px 30px rgba(102, 126, 234, 0.4); }
            50% { box-shadow: 0 10px 40px rgba(102, 126, 234, 0.6); }
        }

        .logo-text h1 {
            font-size: 24px;
            font-weight: 900;
            color: var(--text);
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .logo-text p {
            font-size: 13px;
            color: var(--text-muted);
            font-weight: 600;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 30px;
        }

        .nav-links a {
            color: var(--text);
            text-decoration: none;
            font-weight: 700;
            transition: all 0.3s;
            cursor: pointer;
            position: relative;
            padding: 5px 0;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: 0;
            right: 0;
            width: 0;
            height: 3px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            transition: width 0.3s;
            border-radius: 2px;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .nav-links a:hover {
            color: var(--primary);
        }

        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            font-size: 24px;
            cursor: pointer;
            color: var(--text);
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, rgba(102, 126, 234, 0.9) 0%, rgba(118, 75, 162, 0.9) 100%);
            color: white;
            padding: 100px 0;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg width="100" height="100" xmlns="http://www.w3.org/2000/svg"><circle cx="50" cy="50" r="2" fill="rgba(255,255,255,0.1)"/></svg>');
            animation: moveDots 20s linear infinite;
        }

        @keyframes moveDots {
            0% { transform: translate(0, 0); }
            100% { transform: translate(100px, 100px); }
        }

        .hero-content {
            position: relative;
            z-index: 1;
        }

        .hero h2 {
            font-size: 52px;
            margin-bottom: 20px;
            font-weight: 900;
            text-shadow: 0 4px 20px rgba(0,0,0,0.2);
            animation: slideDown 1s ease;
        }

        @keyframes slideDown {
            from { opacity: 0; transform: translateY(-30px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .hero p {
            font-size: 20px;
            opacity: 0.95;
            max-width: 700px;
            margin: 0 auto 40px;
            font-weight: 500;
        }

        .hero-stats {
            display: flex;
            justify-content: center;
            gap: 50px;
            margin-top: 50px;
            flex-wrap: wrap;
        }

        .hero-stat {
            text-align: center;
            background: rgba(255,255,255,0.15);
            backdrop-filter: blur(10px);
            padding: 25px 40px;
            border-radius: 20px;
            border: 1px solid rgba(255,255,255,0.2);
            transition: transform 0.3s;
        }

        .hero-stat:hover {
            transform: translateY(-10px);
        }

        .hero-stat-number {
            font-size: 48px;
            font-weight: 900;
            color: #fbbf24;
            text-shadow: 0 2px 10px rgba(0,0,0,0.2);
        }

        .hero-stat-label {
            font-size: 16px;
            opacity: 0.9;
            font-weight: 600;
            margin-top: 5px;
        }

        /* Section Styles */
        .section {
            padding: 80px 0;
        }

        .section-title {
            text-align: center;
            margin-bottom: 50px;
        }

        .section-title h3 {
            font-size: 36px;
            color: var(--text);
            margin-bottom: 15px;
            font-weight: 900;
            position: relative;
            display: inline-block;
        }

        .section-title h3::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            border-radius: 2px;
        }

        .section-title p {
            color: var(--text-muted);
            font-size: 18px;
            margin-top: 20px;
        }

        /* Stats Dashboard */
        .stats-dashboard {
            background: var(--card);
            border-radius: 30px;
            padding: 40px;
            box-shadow: 0 20px 60px rgba(0,0,0,0.1);
            margin-bottom: 30px;
            border: 1px solid rgba(255,255,255,0.2);
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 25px;
            margin-bottom: 40px;
        }

        .stat-box {
            background: linear-gradient(135deg, #f0f9ff 0%, #e0f2fe 100%);
            padding: 30px;
            border-radius: 20px;
            text-align: center;
            border: 2px solid #bae6fd;
            transition: all 0.3s;
            position: relative;
            overflow: hidden;
        }

        .stat-box::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 5px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        }

        .stat-box:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(102, 126, 234, 0.2);
        }

        .stat-box i {
            font-size: 40px;
            margin-bottom: 15px;
            display: block;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .stat-box h4 {
            font-size: 36px;
            color: var(--primary);
            margin-bottom: 5px;
            font-weight: 900;
        }

        .stat-box p {
            color: var(--text-muted);
            font-size: 15px;
            font-weight: 700;
        }

        /* Circular Charts */
        .charts-container {
            display: grid;
            grid-template-columns: 2fr 1fr;
            gap: 30px;
        }

        .chart-box {
            background: var(--bg);
            padding: 30px;
            border-radius: 20px;
            border: 1px solid rgba(255,255,255,0.1);
        }

        .chart-box h4 {
            margin-bottom: 25px;
            color: var(--text);
            font-size: 20px;
            font-weight: 800;
        }

        .circular-charts {
            display: flex;
            justify-content: space-around;
            flex-wrap: wrap;
            gap: 30px;
        }

        .circular-item {
            text-align: center;
        }

        .circular-chart {
            position: relative;
            width: 140px;
            height: 140px;
            margin: 0 auto 15px;
        }

        .circular-chart svg {
            transform: rotate(-90deg);
        }

        .circular-chart circle {
            fill: none;
            stroke-width: 12;
        }

        .circular-chart .bg {
            stroke: #e2e8f0;
        }

        .circular-chart .progress {
            stroke-linecap: round;
            transition: stroke-dashoffset 1.5s ease;
        }

        .circular-text {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            font-size: 28px;
            font-weight: 900;
            color: var(--text);
        }

        .circular-label {
            font-size: 15px;
            color: var(--text-muted);
            font-weight: 700;
        }

        /* Rankings */
        .ranking-list {
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        .ranking-item {
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 20px;
            background: var(--bg);
            border-radius: 15px;
            transition: all 0.3s;
            border: 2px solid transparent;
        }

        .ranking-item:hover {
            transform: translateX(-10px);
            border-color: var(--primary);
            box-shadow: 0 10px 30px rgba(102, 126, 234, 0.2);
        }

        .ranking-info {
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .ranking-number {
            width: 45px;
            height: 45px;
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 900;
            font-size: 18px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
        }

        .ranking-number.gold { background: linear-gradient(135deg, #fbbf24 0%, #f59e0b 100%); color: white; }
        .ranking-number.silver { background: linear-gradient(135deg, #94a3b8 0%, #64748b 100%); color: white; }
        .ranking-number.bronze { background: linear-gradient(135deg, #f97316 0%, #ea580c 100%); color: white; }

        .ranking-name {
            font-weight: 800;
            color: var(--text);
            font-size: 16px;
        }

        .ranking-score {
            padding: 8px 20px;
            border-radius: 25px;
            font-size: 14px;
            font-weight: 900;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
        }

        .ranking-score.pink { background: linear-gradient(135deg, #f472b6 0%, #ec4899 100%); color: white; }
        .ranking-score.orange { background: linear-gradient(135deg, #fb923c 0%, #f97316 100%); color: white; }
        .ranking-score.blue { background: linear-gradient(135deg, #60a5fa 0%, #3b82f6 100%); color: white; }

        /* Teacher Section */
        .teacher-card {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            border-radius: 30px;
            padding: 50px;
            display: flex;
            align-items: center;
            gap: 40px;
            margin-bottom: 30px;
            position: relative;
            overflow: hidden;
            box-shadow: 0 20px 60px rgba(102, 126, 234, 0.3);
        }

        .teacher-card::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -10%;
            width: 400px;
            height: 400px;
            background: rgba(255,255,255,0.1);
            border-radius: 50%;
            animation: pulse 4s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); opacity: 0.5; }
            50% { transform: scale(1.1); opacity: 0.3; }
        }

        .teacher-avatar {
            width: 150px;
            height: 150px;
            background: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 80px;
            position: relative;
            z-index: 1;
            box-shadow: 0 20px 60px rgba(0,0,0,0.3);
            border: 5px solid rgba(255,255,255,0.3);
        }

        .teacher-info {
            position: relative;
            z-index: 1;
            flex: 1;
        }

        .teacher-info h3 {
            font-size: 32px;
            margin-bottom: 15px;
            font-weight: 900;
        }

        .teacher-info p {
            opacity: 0.95;
            margin-bottom: 20px;
            line-height: 1.8;
            font-size: 16px;
        }

        .teacher-tags {
            display: flex;
            gap: 12px;
            flex-wrap: wrap;
        }

        .teacher-tag {
            padding: 8px 20px;
            background: rgba(255,255,255,0.2);
            border-radius: 25px;
            font-size: 14px;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255,255,255,0.3);
            font-weight: 600;
        }

        /* Fields Section */
        .fields-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 30px;
            margin-bottom: 30px;
        }

        .field-card {
            background: var(--card);
            border-radius: 24px;
            overflow: hidden;
            box-shadow: 0 10px 40px rgba(0,0,0,0.08);
            transition: all 0.3s;
            border: 1px solid rgba(255,255,255,0.1);
        }

        .field-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 25px 60px rgba(102, 126, 234, 0.2);
        }

        .field-header {
            padding: 30px;
            color: white;
            display: flex;
            align-items: center;
            gap: 20px;
            position: relative;
            overflow: hidden;
        }

        .field-header::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.2) 0%, transparent 70%);
            animation: shimmer 3s infinite;
        }

        @keyframes shimmer {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        .field-header.blue { background: linear-gradient(135deg, #3b82f6 0%, #1d4ed8 100%); }
        .field-header.green { background: linear-gradient(135deg, #10b981 0%, #059669 100%); }
        .field-header.purple { background: linear-gradient(135deg, #8b5cf6 0%, #6d28d9 100%); }

        .field-icon {
            width: 60px;
            height: 60px;
            background: rgba(255,255,255,0.2);
            border-radius: 16px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 28px;
            position: relative;
            z-index: 1;
            backdrop-filter: blur(10px);
        }

        .field-title h4 {
            font-size: 22px;
            margin-bottom: 5px;
            position: relative;
            z-index: 1;
            font-weight: 800;
        }

        .field-title p {
            font-size: 14px;
            opacity: 0.9;
            position: relative;
            z-index: 1;
        }

        .field-body {
            padding: 25px;
        }

        .field-item {
            padding: 15px;
            background: var(--bg);
            border-radius: 12px;
            margin-bottom: 12px;
            font-size: 15px;
            font-weight: 600;
            display: flex;
            align-items: center;
            gap: 12px;
            transition: all 0.3s;
            border-right: 4px solid transparent;
        }

        .field-item:hover {
            border-right-color: var(--primary);
            transform: translateX(-5px);
        }

        .field-item::before {
            content: '✓';
            color: var(--success);
            font-weight: 900;
            font-size: 18px;
        }

        /* Manager Video Section */
        .manager-section {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            padding: 60px;
            border-radius: 30px;
            color: white;
            text-align: center;
            margin: 40px 0;
            position: relative;
            overflow: hidden;
        }

        .manager-section::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg width="60" height="60" xmlns="http://www.w3.org/2000/svg"><circle cx="30" cy="30" r="2" fill="rgba(255,255,255,0.1)"/></svg>');
        }

        .manager-section h3 {
            font-size: 32px;
            margin-bottom: 10px;
            font-weight: 900;
            position: relative;
            z-index: 1;
        }

        .manager-section p {
            font-size: 18px;
            opacity: 0.9;
            margin-bottom: 30px;
            position: relative;
            z-index: 1;
        }

        .video-container {
            position: relative;
            padding-bottom: 56.25%;
            height: 0;
            overflow: hidden;
            border-radius: 20px;
            box-shadow: 0 20px 60px rgba(0,0,0,0.3);
            background: #000;
            z-index: 1;
        }

        .video-container iframe {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            border: none;
        }

        /* Tools Section */
        .tools-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 30px;
            margin-bottom: 30px;
        }

        .tool-card {
            background: var(--card);
            border-radius: 24px;
            padding: 30px;
            box-shadow: 0 10px 40px rgba(0,0,0,0.08);
            transition: all 0.3s;
            border: 1px solid rgba(255,255,255,0.1);
            position: relative;
            overflow: hidden;
        }

        .tool-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        }

        .tool-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 50px rgba(102, 126, 234, 0.15);
        }

        .tool-card h4 {
            margin-bottom: 25px;
            color: var(--text);
            font-size: 20px;
            font-weight: 800;
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .tool-input {
            width: 100%;
            padding: 15px;
            border: 2px solid #e2e8f0;
            border-radius: 12px;
            margin-bottom: 15px;
            font-family: inherit;
            font-size: 15px;
            background: var(--bg);
            color: var(--text);
            transition: all 0.3s;
        }

        .tool-input:focus {
            outline: none;
            border-color: var(--primary);
            box-shadow: 0 0 0 4px rgba(102, 126, 234, 0.1);
        }

        .tool-btn {
            width: 100%;
            padding: 15px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            border: none;
            border-radius: 12px;
            cursor: pointer;
            font-family: inherit;
            font-weight: 800;
            font-size: 16px;
            transition: all 0.3s;
            box-shadow: 0 4px 15px rgba(102, 126, 234, 0.4);
        }

        .tool-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 25px rgba(102, 126, 234, 0.5);
        }

        .tool-result {
            margin-top: 20px;
            padding: 20px;
            background: var(--bg);
            border-radius: 12px;
            text-align: center;
            font-weight: 800;
            color: var(--primary);
            min-height: 60px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 18px;
            border: 2px dashed var(--primary);
        }

        .color-preview {
            width: 100%;
            height: 80px;
            border-radius: 12px;
            margin-bottom: 15px;
            border: 3px solid #e2e8f0;
            transition: all 0.3s;
        }

        /* Code Editor */
        .code-editor {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
            height: 350px;
        }

        .code-input, .code-output {
            width: 100%;
            height: 100%;
            padding: 20px;
            border: 2px solid #e2e8f0;
            border-radius: 12px;
            font-family: 'Courier New', monospace;
            font-size: 14px;
            resize: none;
            background: var(--bg);
            color: var(--text);
            transition: all 0.3s;
        }

        .code-input:focus {
            border-color: var(--primary);
            box-shadow: 0 0 0 4px rgba(102, 126, 234, 0.1);
        }

        .code-output {
            background: #1e293b;
            color: #10b981;
            border-color: #334155;
        }

        /* Timeline */
        .timeline {
            position: relative;
            padding: 20px 0;
        }

        .timeline::before {
            content: '';
            position: absolute;
            right: 30px;
            top: 0;
            bottom: 0;
            width: 4px;
            background: linear-gradient(to bottom, #667eea, #764ba2);
            border-radius: 2px;
        }

        .timeline-item {
            position: relative;
            padding-right: 80px;
            margin-bottom: 40px;
        }

        .timeline-dot {
            position: absolute;
            right: 20px;
            width: 24px;
            height: 24px;
            background: linear-gradient(135deg, #fbbf24 0%, #f59e0b 100%);
            border-radius: 50%;
            border: 4px solid var(--card);
            box-shadow: 0 0 0 4px #fbbf24;
            z-index: 1;
        }

        .timeline-content {
            background: var(--card);
            padding: 25px;
            border-radius: 16px;
            box-shadow: 0 10px 40px rgba(0,0,0,0.08);
            border: 1px solid rgba(255,255,255,0.1);
            transition: all 0.3s;
        }

        .timeline-content:hover {
            transform: translateX(-10px);
            box-shadow: 0 15px 50px rgba(102, 126, 234, 0.15);
        }

        .timeline-date {
            color: var(--primary);
            font-weight: 900;
            margin-bottom: 8px;
            font-size: 18px;
        }

        .timeline-content h4 {
            margin-bottom: 8px;
            color: var(--text);
            font-size: 20px;
            font-weight: 800;
        }

        .timeline-content p {
            color: var(--text-muted);
            font-size: 15px;
            line-height: 1.6;
        }

        /* Accordion */
        .accordion {
            background: var(--card);
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 10px 40px rgba(0,0,0,0.08);
            border: 1px solid rgba(255,255,255,0.1);
        }

        .accordion-item {
            border-bottom: 1px solid var(--bg);
        }

        .accordion-header {
            padding: 25px;
            cursor: pointer;
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-weight: 800;
            font-size: 16px;
            transition: all 0.3s;
            background: var(--card);
        }

        .accordion-header:hover {
            background: var(--bg);
        }

        .accordion-header.active {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
        }

        .accordion-body {
            padding: 0 25px;
            max-height: 0;
            overflow: hidden;
            transition: all 0.3s;
            background: var(--bg);
        }

        .accordion-body.active {
            padding: 25px;
            max-height: 300px;
        }

        .accordion-body p {
            color: var(--text-muted);
            line-height: 1.8;
        }

        /* Grades System Card */
        .grades-card {
            background: linear-gradient(135deg, #10b981 0%, #059669 100%);
            color: white;
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }

        .grades-card::after {
            content: '🔓';
            position: absolute;
            top: 20px;
            left: 20px;
            font-size: 24px;
            animation: bounce 2s infinite;
        }

        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

        .grades-card:hover {
            transform: translateY(-10px) scale(1.02);
        }

        /* Login Modal */
        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0,0,0,0.8);
            backdrop-filter: blur(10px);
            display: none;
            align-items: center;
            justify-content: center;
            z-index: 10000;
            opacity: 0;
            transition: opacity 0.3s;
        }

        .modal-overlay.active {
            display: flex;
            opacity: 1;
        }

        .login-modal {
            background: var(--card);
            border-radius: 30px;
            padding: 50px;
            width: 90%;
            max-width: 450px;
            box-shadow: 0 25px 80px rgba(0,0,0,0.3);
            transform: scale(0.9);
            transition: transform 0.3s;
            position: relative;
            overflow: hidden;
        }

        .modal-overlay.active .login-modal {
            transform: scale(1);
        }

        .login-modal::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 5px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        }

        .login-header {
            text-align: center;
            margin-bottom: 30px;
        }

        .login-header h3 {
            font-size: 28px;
            color: var(--text);
            margin-bottom: 10px;
            font-weight: 900;
        }

        .login-header p {
            color: var(--text-muted);
        }

        .login-icon {
            width: 100px;
            height: 100px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 50px;
            margin: 0 auto 20px;
            color: white;
            box-shadow: 0 10px 30px rgba(102, 126, 234, 0.4);
        }

        .login-input {
            width: 100%;
            padding: 18px;
            border: 2px solid #e2e8f0;
            border-radius: 15px;
            margin-bottom: 20px;
            font-family: inherit;
            font-size: 16px;
            background: var(--bg);
            color: var(--text);
            transition: all 0.3s;
        }

        .login-input:focus {
            outline: none;
            border-color: var(--primary);
            box-shadow: 0 0 0 4px rgba(102, 126, 234, 0.1);
        }

        .login-btn {
            width: 100%;
            padding: 18px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            border: none;
            border-radius: 15px;
            cursor: pointer;
            font-family: inherit;
            font-weight: 800;
            font-size: 18px;
            transition: all 0.3s;
            box-shadow: 0 4px 15px rgba(102, 126, 234, 0.4);
        }

        .login-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 25px rgba(102, 126, 234, 0.5);
        }

        .close-modal {
            position: absolute;
            top: 20px;
            right: 20px;
            background: none;
            border: none;
            font-size: 28px;
            cursor: pointer;
            color: var(--text-muted);
            transition: color 0.3s;
            width: 40px;
            height: 40px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
        }

        .close-modal:hover {
            color: var(--danger);
            background: rgba(239, 68, 68, 0.1);
        }

        /* Teacher Dashboard */
        .teacher-dashboard {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: var(--bg);
            z-index: 9999;
            overflow-y: auto;
        }

        .teacher-dashboard.active {
            display: block;
        }

        .dashboard-header {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 30px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 10px 40px rgba(102, 126, 234, 0.3);
        }

        .dashboard-header h2 {
            font-size: 24px;
            font-weight: 900;
        }

        .logout-btn {
            padding: 12px 25px;
            background: rgba(255,255,255,0.2);
            border: none;
            color: white;
            border-radius: 10px;
            cursor: pointer;
            font-family: inherit;
            font-weight: 700;
            transition: all 0.3s;
            backdrop-filter: blur(10px);
        }

        .logout-btn:hover {
            background: rgba(255,255,255,0.3);
            transform: scale(1.05);
        }

        .dashboard-content {
            padding: 40px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .student-form {
            background: var(--card);
            padding: 40px;
            border-radius: 24px;
            box-shadow: 0 10px 40px rgba(0,0,0,0.08);
            margin-bottom: 30px;
            border: 1px solid rgba(255,255,255,0.1);
        }

        .student-form h3 {
            margin-bottom: 25px;
            color: var(--text);
            font-size: 22px;
            font-weight: 800;
        }

        .form-row {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
            margin-bottom: 20px;
        }

        .student-list {
            background: var(--card);
            padding: 40px;
            border-radius: 24px;
            box-shadow: 0 10px 40px rgba(0,0,0,0.08);
            border: 1px solid rgba(255,255,255,0.1);
        }

        .student-list h3 {
            margin-bottom: 25px;
            color: var(--text);
            font-size: 22px;
            font-weight: 800;
        }

        .student-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px;
            background: var(--bg);
            border-radius: 15px;
            margin-bottom: 15px;
            border-right: 4px solid var(--primary);
            transition: all 0.3s;
        }

        .student-item:hover {
            transform: translateX(-5px);
            box-shadow: 0 5px 20px rgba(0,0,0,0.1);
        }

        .student-name {
            font-weight: 800;
            color: var(--text);
            font-size: 16px;
        }

        .student-date {
            color: var(--text-muted);
            font-size: 14px;
        }

        .delete-btn {
            background: var(--danger);
            color: white;
            border: none;
            padding: 8px 16px;
            border-radius: 8px;
            cursor: pointer;
            font-family: inherit;
            font-weight: 700;
            transition: all 0.3s;
        }

        .delete-btn:hover {
            transform: scale(1.05);
            box-shadow: 0 4px 15px rgba(239, 68, 68, 0.4);
        }

        /* Toast Notification */
        .toast {
            position: fixed;
            bottom: 30px;
            left: 50%;
            transform: translateX(-50%) translateY(100px);
            background: var(--dark);
            color: white;
            padding: 18px 40px;
            border-radius: 15px;
            box-shadow: 0 10px 40px rgba(0,0,0,0.3);
            z-index: 10001;
            opacity: 0;
            transition: all 0.3s;
            font-weight: 700;
            font-size: 16px;
        }

        .toast.show {
            transform: translateX(-50%) translateY(0);
            opacity: 1;
        }

        .toast.error {
            background: var(--danger);
        }

        .toast.success {
            background: var(--success);
        }

        /* Footer */
        footer {
            background: var(--card);
            padding: 60px 0 30px;
            border-top: 1px solid rgba(255,255,255,0.1);
            margin-top: 80px;
        }

        .footer-content {
            display: grid;
            grid-template-columns: 2fr 1fr 1fr;
            gap: 50px;
            margin-bottom: 40px;
        }

        .footer-section h4 {
            color: var(--text);
            margin-bottom: 20px;
            font-size: 20px;
            font-weight: 800;
        }

        .footer-section p, .footer-section a {
            color: var(--text-muted);
            text-decoration: none;
            line-height: 2;
            font-size: 15px;
            transition: color 0.3s;
        }

        .footer-section a:hover {
            color: var(--primary);
        }

        .developer-credit {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 30px;
            border-radius: 20px;
            text-align: center;
            margin-top: 30px;
            box-shadow: 0 10px 40px rgba(102, 126, 234, 0.3);
        }

        .developer-credit p {
            color: white !important;
            margin: 8px 0;
        }

        .developer-name {
            font-size: 24px;
            font-weight: 900;
            margin-bottom: 5px;
        }

        /* Responsive */
        @media (max-width: 968px) {
            .nav-links {
                display: none;
            }

            .mobile-menu-btn {
                display: block;
            }

            .charts-container {
                grid-template-columns: 1fr;
            }

            .code-editor {
                grid-template-columns: 1fr;
                height: auto;
            }

            .code-input, .code-output {
                height: 250px;
            }

            .teacher-card {
                flex-direction: column;
                text-align: center;
                padding: 30px;
            }

            .footer-content {
                grid-template-columns: 1fr;
                text-align: center;
                gap: 30px;
            }

            .hero h2 {
                font-size: 36px;
            }

            .hero-stats {
                gap: 20px;
            }

            .hero-stat {
                padding: 20px 30px;
            }

            .form-row {
                grid-template-columns: 1fr;
            }

            .manager-section {
                padding: 30px;
            }
        }

        /* Animations */
        .fade-in {
            opacity: 0;
            transform: translateY(40px);
            transition: all 0.8s ease;
        }

        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }

        /* Scrollbar */
        ::-webkit-scrollbar {
            width: 12px;
        }

        ::-webkit-scrollbar-track {
            background: var(--bg);
        }

        ::-webkit-scrollbar-thumb {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            border-radius: 6px;
            border: 3px solid var(--bg);
        }

        ::-webkit-scrollbar-thumb:hover {
            background: linear-gradient(135deg, #764ba2 0%, #667eea 100%);
        }

        /* Empty State */
        .empty-state {
            text-align: center;
            padding: 60px 20px;
            color: var(--text-muted);
        }

        .empty-state i {
            font-size: 64px;
            margin-bottom: 20px;
            opacity: 0.3;
        }

        .empty-state p {
            font-size: 18px;
            font-weight: 600;
        }
    </style>
</head>
<body>
    <div class="bg-animation"></div>
    
    <!-- Loading Screen -->
    <div class="loader" id="loader">
        <div class="loader-logo">🏫</div>
        <div class="loader-text">مدرسه کار و دانش شهید عظیمی</div>
        <div class="loader-subtext">در حال بارگذاری...</div>
    </div>

    <!-- Toast -->
    <div class="toast" id="toast"></div>

    <!-- Login Modal -->
    <div class="modal-overlay" id="loginModal">
        <div class="login-modal">
            <button class="close-modal" onclick="closeLoginModal()">×</button>
            <div class="login-header">
                <div class="login-icon">👨‍🏫</div>
                <h3>ورود معلم</h3>
                <p>سیستم مدیریت نمرات</p>
            </div>
            <input type="text" class="login-input" id="loginUsername" placeholder="نام کاربری">
            <input type="password" class="login-input" id="loginPassword" placeholder="رمز عبور">
            <button class="login-btn" onclick="checkLogin()">ورود به سیستم</button>
        </div>
    </div>

    <!-- Teacher Dashboard -->
    <div class="teacher-dashboard" id="teacherDashboard">
        <div class="dashboard-header">
            <h2>👨‍🏫 پنل مدیریت معلم - جناب آقای سلخوری</h2>
            <button class="logout-btn" onclick="logout()">خروج</button>
        </div>
        <div class="dashboard-content">
            <div class="student-form">
                <h3>➕ افزودن دانش‌آموز جدید</h3>
                <div class="form-row">
                    <input type="text" class="tool-input" id="studentName" placeholder="نام و نام خانوادگی دانش‌آموز" style="margin:0;">
                    <input type="text" class="tool-input" id="studentId" placeholder="شماره دانش‌آموزی" style="margin:0;">
                </div>
                <button class="tool-btn" onclick="addStudent()">💾 ذخیره دانش‌آموز</button>
            </div>
            
            <div class="student-list">
                <h3>📋 لیست دانش‌آموزان</h3>
                <div id="studentsListContainer">
                    <div class="empty-state">
                        <i>👥</i>
                        <p>هنوز دانش‌آموزی ثبت نشده است</p>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Main Content -->
    <div id="mainContent">
        <!-- Header -->
        <header>
            <div class="top-bar">
                <div class="container">
                    <div class="top-bar-content">
                        <div class="contact-info">
                            <span><i>📞</i> 028-3332716</span>
                            <span><i>📍</i> قزوین، خیابان سعدی، شیخ آباد، قهرمانی</span>
                            <span><i>📮</i> 3419667816</span>
                        </div>
                        <div class="header-actions">
                            <button class="theme-toggle" onclick="toggleTheme()">🌓 تغییر تم</button>
                        </div>
                    </div>
                </div>
            </div>
            <nav class="container">
                <div class="logo">
                    <div class="logo-icon">🏫</div>
                    <div class="logo-text">
                        <h1>کار و دانش شهید عظیمی</h1>
                        <p>قزوین</p>
                    </div>
                </div>
                <ul class="nav-links">
                    <li><a onclick="scrollToSection('stats')">📊 آمار</a></li>
                    <li><a onclick="scrollToSection('fields')">🎓 رشته‌ها</a></li>
                    <li><a onclick="scrollToSection('manager')">🎥 مدیریت</a></li>
                    <li><a onclick="scrollToSection('tools')">🛠️ ابزارها</a></li>
                    <li><a onclick="scrollToSection('timeline')">📜 تاریخچه</a></li>
                    <li><a onclick="showToast('وارد نشده', 'error')">🖼️ گالری</a></li>
                    <li><a onclick="showToast('وارد نشده', 'error')">📝 نظرات</a></li>
                </ul>
                <button class="mobile-menu-btn" onclick="toggleMobileMenu()">☰</button>
            </nav>
        </header>

        <!-- Hero -->
        <section class="hero">
            <div class="container">
                <div class="hero-content">
                    <h2>مدرسه کار و دانش شهید عظیمی</h2>
                    <p>آموزش مهارتی، آینده‌سازان حرفه‌ای | بیش از دو دهه تجربه در آموزش فنی و حرفه‌ای</p>
                    <div class="hero-stats">
                        <div class="hero-stat">
                            <div class="hero-stat-number">467</div>
                            <div class="hero-stat-label">دانش‌آموز</div>
                        </div>
                        <div class="hero-stat">
                            <div class="hero-stat-number">32</div>
                            <div class="hero-stat-label">معلم</div>
                        </div>
                        <div class="hero-stat">
                            <div class="hero-stat-number">7</div>
                            <div class="hero-stat-label">رشته</div>
                        </div>
                        <div class="hero-stat">
                            <div class="hero-stat-number">89%</div>
                            <div class="hero-stat-label">قبولی</div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Stats Dashboard -->
        <section class="section" id="stats">
            <div class="container">
                <div class="section-title fade-in">
                    <h3>📊 داشبورد مدیریت</h3>
                    <p>آمار و ارقام مدرسه در سال تحصیلی 1403-1404</p>
                </div>
                
                <div class="stats-dashboard fade-in">
                    <div class="stats-grid">
                        <div class="stat-box">
                            <i>👨‍🎓</i>
                            <h4>467</h4>
                            <p>تعداد دانش‌آموزان</p>
                        </div>
                        <div class="stat-box">
                            <i>👨‍🏫</i>
                            <h4>32</h4>
                            <p>تعداد معلمان</p>
                        </div>
                        <div class="stat-box">
                            <i>🎓</i>
                            <h4>7</h4>
                            <p>رشته تحصیلی</p>
                        </div>
                        <div class="stat-box">
                            <i>🏆</i>
                            <h4>89%</h4>
                            <p>نرخ قبولی</p>
                        </div>
                    </div>

                    <div class="charts-container">
                        <div class="chart-box">
                            <h4>📈 امتیاز مدرسه</h4>
                            <div class="circular-charts">
                                <div class="circular-item">
                                    <div class="circular-chart">
                                        <svg width="140" height="140">
                                            <circle class="bg" cx="70" cy="70" r="60"></circle>
                                            <circle class="progress" cx="70" cy="70" r="60" 
                                                stroke-dasharray="377" stroke-dashoffset="377" data-percent="89" stroke="#10b981"></circle>
                                        </svg>
                                        <div class="circular-text">89%</div>
                                    </div>
                                    <div class="circular-label">میزان محبوبیت</div>
                                </div>
                                <div class="circular-item">
                                    <div class="circular-chart">
                                        <svg width="140" height="140">
                                            <circle class="bg" cx="70" cy="70" r="60"></circle>
                                            <circle class="progress" cx="70" cy="70" r="60" 
                                                stroke-dasharray="377" stroke-dashoffset="377" data-percent="78" stroke="#f59e0b"></circle>
                                        </svg>
                                        <div class="circular-text">78%</div>
                                    </div>
                                    <div class="circular-label">دانش‌آموزان</div>
                                </div>
                                <div class="circular-item">
                                    <div class="circular-chart">
                                        <svg width="140" height="140">
                                            <circle class="bg" cx="70" cy="70" r="60"></circle>
                                            <circle class="progress" cx="70" cy="70" r="60" 
                                                stroke-dasharray="377" stroke-dashoffset="377" data-percent="82" stroke="#3b82f6"></circle>
                                        </svg>
                                        <div class="circular-text">82%</div>
                                    </div>
                                    <div class="circular-label">معلمان</div>
                                </div>
                            </div>
                        </div>

                        <div class="chart-box">
                            <h4>🏅 رتبه مدرسه</h4>
                            <div class="ranking-list">
                                <div class="ranking-item">
                                    <div class="ranking-info">
                                        <div class="ranking-number gold">1</div>
                                        <span class="ranking-name">کشور</span>
                                    </div>
                                    <span class="ranking-score pink">505</span>
                                </div>
                                <div class="ranking-item">
                                    <div class="ranking-info">
                                        <div class="ranking-number silver">2</div>
                                        <span class="ranking-name">استان</span>
                                    </div>
                                    <span class="ranking-score orange">8</span>
                                </div>
                                <div class="ranking-item">
                                    <div class="ranking-info">
                                        <div class="ranking-number bronze">3</div>
                                        <span class="ranking-name">ناحیه</span>
                                    </div>
                                    <span class="ranking-score blue">3</span>
                                </div>
                            </div>
                            <p style="text-align: center; margin-top: 20px; color: var(--text-muted); font-size: 14px; font-weight: 600;">
                                از 30 مدرسه | از 139 مدرسه | از 8411 مدرسه
                            </p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Teacher Section -->
        <section class="section">
            <div class="container">
                <div class="section-title fade-in">
                    <h3>👨‍🏫 کادر آموزشی</h3>
                    <p>اساتید مجرب و متخصص</p>
                </div>
                
                <div class="teacher-card fade-in">
                    <div class="teacher-avatar">👨‍🏫</div>
                    <div class="teacher-info">
                        <h3>جناب آقای مهندس هادی سلخوری</h3>
                        <p>هنرآموز تولید محتوای الکترونیکی و طراحی وب<br>
                        دبیرستان کار و دانش شهید عظیمی - قزوین<br>
                        تدریس در پایه دهم - رشته تولید محتوا</p>
                        <div class="teacher-tags">
                            <span class="teacher-tag">🎨 تولید محتوا</span>
                            <span class="teacher-tag">💻 برنامه‌نویسی</span>
                            <span class="teacher-tag">🌐 طراحی وب</span>
                            <span class="teacher-tag">📱 توسعه اپلیکیشن</span>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Fields Section -->
        <section class="section" id="fields">
            <div class="container">
                <div class="section-title fade-in">
                    <h3>🎓 رشته‌های تحصیلی</h3>
                    <p>7 رشته فنی و حرفه‌ای</p>
                </div>
                
                <div class="fields-grid">
                    <div class="field-card fade-in">
                        <div class="field-header blue">
                            <div class="field-icon">⚡</div>
                            <div class="field-title">
                                <h4>برق و الکترونیک</h4>
                                <p>3 رشته</p>
                            </div>
                        </div>
                        <div class="field-body">
                            <div class="field-item">الکترونیک صنعتی</div>
                            <div class="field-item">برق ساختمان</div>
                            <div class="field-item">برق صنعتی</div>
                        </div>
                    </div>

                    <div class="field-card fade-in">
                        <div class="field-header green">
                            <div class="field-icon">📱</div>
                            <div class="field-title">
                                <h4>ICT و مخابرات</h4>
                                <p>1 رشته</p>
                            </div>
                        </div>
                        <div class="field-body">
                            <div class="field-item">تعمیر تلفن‌های رومیزی و همراه</div>
                        </div>
                    </div>

                    <div class="field-card fade-in">
                        <div class="field-header purple">
                            <div class="field-icon">💻</div>
                            <div class="field-title">
                                <h4>کامپیوتر و IT</h4>
                                <p>3 رشته</p>
                            </div>
                        </div>
                        <div class="field-body">
                            <div class="field-item">تولید محتوای الکترونیکی</div>
                            <div class="field-item">تولید و توسعه پایگاه‌های اینترنتی</div>
                            <div class="field-item">طراحی و توسعه صفحات وب</div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Manager Video Section -->
        <section class="section" id="manager">
            <div class="container">
                <div class="manager-section fade-in">
                    <h3>🎥 صحبت‌های مدیریت محترم مدرسه</h3>
                    <p>جناب آقای سعید معزی‌زاده</p>
                    <div class="video-container">
                        <iframe src="https://www.aparat.com/video/video/embed/videohash/mud61je/vt/frame" allowFullScreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"></iframe>
                    </div>
                </div>
            </div>
        </section>

        <!-- Tools Section -->
        <section class="section" id="tools">
            <div class="container">
                <div class="section-title fade-in">
                    <h3>🛠️ ابزارهای تعاملی</h3>
                    <p>ابزارهای کمک آموزشی</p>
                </div>
                
                <div class="tools-grid">
                    <!-- Grade Calculator -->
                    <div class="tool-card fade-in">
                        <h4>🧮 ماشین حساب نمره</h4>
                        <input type="number" class="tool-input" id="grade1" placeholder="نمره اول (ضریب 2)">
                        <input type="number" class="tool-input" id="grade2" placeholder="نمره دوم (ضریب 2)">
                        <input type="number" class="tool-input" id="grade3" placeholder="نمره سوم (ضریب 1)">
                        <button class="tool-btn" onclick="calculateGrade()">محاسبه معدل</button>
                        <div class="tool-result" id="gradeResult">منتظر ورودی...</div>
                    </div>

                    <!-- Unit Converter -->
                    <div class="tool-card fade-in">
                        <h4>⚡ تبدیل واحد برق</h4>
                        <select class="tool-input" id="unitType">
                            <option value="v-a">ولت ←→ آمپر (با مقاومت)</option>
                            <option value="w-v">وات ←→ ولت</option>
                            <option value="kw-w">کیلووات ←→ وات</option>
                        </select>
                        <input type="number" class="tool-input" id="unitInput" placeholder="مقدار ورودی">
                        <input type="number" class="tool-input" id="unitHelper" placeholder="مقاومت/جریان کمکی">
                        <button class="tool-btn" onclick="convertUnit()">تبدیل</button>
                        <div class="tool-result" id="unitResult">منتظر ورودی...</div>
                    </div>

                    <!-- Color Picker -->
                    <div class="tool-card fade-in">
                        <h4>🎨 کد رنگ آنلاین</h4>
                        <div class="color-preview" id="colorPreview" style="background: #3b82f6;"></div>
                        <input type="color" class="tool-input" id="colorInput" value="#3b82f6" oninput="updateColor()">
                        <input type="text" class="tool-input" id="colorCode" value="#3b82f6" readonly>
                        <button class="tool-btn" onclick="copyColor()">کپی کد رنگ</button>
                    </div>
                </div>

                <!-- Code Editor -->
                <div class="tool-card fade-in" style="margin-top: 30px;">
                    <h4>💻 ادیتور کد (HTML/CSS/JS)</h4>
                    <div class="code-editor">
                        <textarea class="code-input" id="codeInput" placeholder="کد HTML/CSS/JS خود را اینجا بنویسید..."><style>
    .box {
        background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        color: white;
        padding: 30px;
        text-align: center;
        border-radius: 15px;
        font-family: 'Vazirmatn', sans-serif;
        font-size: 18px;
        font-weight: 700;
        box-shadow: 0 10px 30px rgba(0,0,0,0.2);
    }
</style>
<div class="box">
    👋 سلام! این یک تست است.<br>
    🎨 طراحی زیبا با CSS
</div></textarea>
                        <iframe class="code-output" id="codeOutput"></iframe>
                    </div>
                    <button class="tool-btn" onclick="runCode()" style="margin-top: 20px;">▶️ اجرای کد</button>
                </div>
            </div>
        </section>

        <!-- Timeline Section -->
        <section class="section" id="timeline">
            <div class="container">
                <div class="section-title fade-in">
                    <h3>📜 تاریخچه مدرسه</h3>
                    <p>دستاوردها و افتخارات</p>
                </div>
                
                <div class="timeline fade-in">
                    <div class="timeline-item">
                        <div class="timeline-dot"></div>
                        <div class="timeline-content">
                            <div class="timeline-date">1403</div>
                            <h4>رتبه 505 کشوری</h4>
                            <p>کسب رتبه برتر در جشنواره خیرین مدرسه‌ساز</p>
                        </div>
                    </div>
                    <div class="timeline-item">
                        <div class="timeline-dot"></div>
                        <div class="timeline-content">
                            <div class="timeline-date">1402</div>
                            <h4>تجهیز کارگاه‌های جدید</h4>
                            <p>راه‌اندازی کارگاه تولید محتوای دیجیتال</p>
                        </div>
                    </div>
                    <div class="timeline-item">
                        <div class="timeline-dot"></div>
                        <div class="timeline-content">
                            <div class="timeline-date">1400</div>
                            <h4>افتتاح ساختمان جدید</h4>
                            <p>افزایش ظرفیت پذیرش به 500 دانش‌آموز</p>
                        </div>
                    </div>
                    <div class="timeline-item">
                        <div class="timeline-dot"></div>
                        <div class="timeline-content">
                            <div class="timeline-date">1384</div>
                            <h4>تأسیس مدرسه</h4>
                            <p>آغاز فعالیت با 3 رشته فنی</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- FAQ Section -->
        <section class="section">
            <div class="container">
                <div class="section-title fade-in">
                    <h3>❓ سوالات متداول</h3>
                    <p>پاسخ به پرسش‌های رایج</p>
                </div>
                
                <div class="accordion fade-in">
                    <div class="accordion-item">
                        <div class="accordion-header" onclick="toggleAccordion(this)">
                            <span>شرایط ثبت‌نام در مدرسه چیست؟</span>
                            <span>▼</span>
                        </div>
                        <div class="accordion-body">
                            <p>دارا بودن مدرک سیکل یا دوره اول متوسطه، قبولی در آزمون ورودی، و تکمیل فرم ثبت‌نام به همراه مدارک شناسایی.</p>
                        </div>
                    </div>
                    <div class="accordion-item">
                        <div class="accordion-header" onclick="toggleAccordion(this)">
                            <span>آیا مدرسه خوابگاه دارد؟</span>
                            <span>▼</span>
                        </div>
                        <div class="accordion-body">
                            <p>خیر، فعلاً خوابگاه نداریم اما سرویس ایاب و ذهاب برای مناطق دورتر فراهم است.</p>
                        </div>
                    </div>
                    <div class="accordion-item">
                        <div class="accordion-header" onclick="toggleAccordion(this)">
                            <span>مدارک ارائه شده چیست؟</span>
                            <span>▼</span>
                        </div>
                        <div class="accordion-body">
                            <p>دیپلم 3 ساله فنی و حرفه‌ای + گواهینامه مهارتی سطح 2 فنی و حرفه‌ای کشور.</p>
                        </div>
                    </div>
                    <div class="accordion-item">
                        <div class="accordion-header" onclick="toggleAccordion(this)">
                            <span>آیا امکان ادامه تحصیل وجود دارد؟</span>
                            <span>▼</span>
                        </div>
                        <div class="accordion-body">
                            <p>بله، فارغ‌التحصیلان می‌توانند در دانشگاه‌های فنی و حرفه‌ای یا دانشگاه آزاد ادامه تحصیل دهند.</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Development Features -->
        <section class="section" style="background: var(--bg);">
            <div class="container">
                <div class="section-title fade-in">
                    <h3>🔒 بخش‌های در دست توسعه</h3>
                    <p>به زودی فعال می‌شوند</p>
                </div>
                
                <div class="tools-grid">
                    <div class="tool-card disabled-item fade-in" onclick="showToast('وارد نشده', 'error')">
                        <h4>🖼️ گالری تصاویر</h4>
                        <p style="color: var(--text-muted); margin-top: 15px; line-height: 1.8;">مشاهده عکس‌های مدرسه، مراسم و فعالیت‌ها</p>
                    </div>
                    
                    <!-- Grades System - Active -->
                    <div class="tool-card grades-card fade-in" onclick="openLoginModal()">
                        <h4>📊 سیستم نمرات</h4>
                        <p style="margin-top: 15px; line-height: 1.8; font-weight: 600;">ورود معلم به سیستم مدیریت نمرات و دانش‌آموزان</p>
                        <div style="margin-top: 20px; padding: 15px; background: rgba(255,255,255,0.2); border-radius: 10px; text-align: center; font-weight: 700;">
                            🔓 کلیک کنید برای ورود
                        </div>
                    </div>
                    
                    <div class="tool-card disabled-item fade-in" onclick="showToast('وارد نشده', 'error')">
                        <h4>🗺️ نقشه موقعیت</h4>
                        <p style="color: var(--text-muted); margin-top: 15px; line-height: 1.8;">مشاهده موقعیت دقیق مدرسه روی نقشه</p>
                    </div>
                    <div class="tool-card disabled-item fade-in" onclick="showToast('وارد نشده', 'error')">
                        <h4>💬 نظرات و پیشنهادات</h4>
                        <p style="color: var(--text-muted); margin-top: 15px; line-height: 1.8;">ارسال نظر، پیشنهاد یا انتقاد</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Footer -->
        <footer>
            <div class="container">
                <div class="footer-content">
                    <div class="footer-section">
                        <h4>📍 آدرس مدرسه</h4>
                        <p>قزوین، بخش مرکزی، خیابان سعدی<br>
                        خیابان شیخ آباد، کوچه قهرمانی<br>
                        کدپستی: 3419667816<br>
                        تلفن: 028-3332716</p>
                    </div>
                    <div class="footer-section">
                        <h4>🔗 لینک‌های مفید</h4>
                        <p>
                            <a href="#">سازمان آموزش و پرورش</a><br>
                            <a href="#">فنی و حرفه‌ای</a><br>
                            <a href="#">وزارت آموزش</a><br>
                            <a href="#">سنجش کشور</a>
                        </p>
                    </div>
                    <div class="footer-section">
                        <h4>📞 تماس با ما</h4>
                        <p>
                            تلفن: 028-3332716<br>
                            موبایل: 0912XXXXXXX<br>
                            ایمیل: info@azimischool.com<br>
                            ساعات کاری: 7:30 - 14:00
                        </p>
                    </div>
                </div>
                
                <div class="developer-credit fade-in">
                    <p class="developer-name">👨‍💻 محمدرضا دولتی</p>
                    <p>طراح و توسعه‌دهنده این سایت</p>
                    <p>هنرآموز: جناب آقای مهندس هادی سلخوری | پایه دهم - تولید محتوا</p>
                    <p style="margin-top: 15px; font-size: 14px; opacity: 0.9;">© 1403 - تمامی حقوق محفوظ است</p>
                </div>
            </div>
        </footer>
    </div>

    <script>
        // Loading Screen
        window.addEventListener('load', function() {
            setTimeout(() => {
                document.getElementById('loader').classList.add('hidden');
                animateCharts();
                initScrollAnimations();
                runCode();
            }, 1500);
        });

        // Toast Notification
        function showToast(message, type = 'info') {
            const toast = document.getElementById('toast');
            toast.textContent = message;
            toast.className = 'toast show ' + type;
            
            setTimeout(() => {
                toast.classList.remove('show');
            }, 3000);
        }

        // Theme Toggle
        function toggleTheme() {
            const html = document.documentElement;
            const currentTheme = html.getAttribute('data-theme');
            const newTheme = currentTheme === 'dark' ? 'light' : 'dark';
            html.setAttribute('data-theme', newTheme);
            localStorage.setItem('theme', newTheme);
            showToast(newTheme === 'dark' ? 'حالت تاریک فعال شد 🌙' : 'حالت روشن فعال شد ☀️', 'success');
        }

        // Load saved theme
        const savedTheme = localStorage.getItem('theme');
        if (savedTheme) {
            document.documentElement.setAttribute('data-theme', savedTheme);
        }

        // Scroll to Section
        function scrollToSection(id) {
            const element = document.getElementById(id);
            if (element) {
                element.scrollIntoView({ behavior: 'smooth' });
            }
        }

        // Mobile Menu Toggle
        function toggleMobileMenu() {
            const navLinks = document.querySelector('.nav-links');
            navLinks.style.display = navLinks.style.display === 'flex' ? 'none' : 'flex';
            navLinks.style.position = 'absolute';
            navLinks.style.top = '100%';
            navLinks.style.left = '0';
            navLinks.style.right = '0';
            navLinks.style.background = 'var(--card)';
            navLinks.style.flexDirection = 'column';
            navLinks.style.padding = '20px';
            navLinks.style.boxShadow = '0 10px 20px rgba(0,0,0,0.1)';
            navLinks.style.zIndex = '999';
        }

        // Animate Circular Charts
        function animateCharts() {
            const circles = document.querySelectorAll('.circular-chart .progress');
            circles.forEach(circle => {
                const percent = circle.getAttribute('data-percent');
                const circumference = 2 * Math.PI * 60;
                const offset = circumference - (percent / 100) * circumference;
                circle.style.strokeDashoffset = offset;
            });
        }

        // Scroll Animations
        function initScrollAnimations() {
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('visible');
                    }
                });
            }, { threshold: 0.1 });

            document.querySelectorAll('.fade-in').forEach(el => observer.observe(el));
        }

        // Grade Calculator
        function calculateGrade() {
            const g1 = parseFloat(document.getElementById('grade1').value) || 0;
            const g2 = parseFloat(document.getElementById('grade2').value) || 0;
            const g3 = parseFloat(document.getElementById('grade3').value) || 0;
            
            const avg = ((g1 * 2) + (g2 * 2) + (g3 * 1)) / 5;
            const result = document.getElementById('gradeResult');
            
            if (avg >= 17) {
                result.innerHTML = `معدل: ${avg.toFixed(2)} <br> 🌟 عالی`;
                result.style.color = '#10b981';
                result.style.borderColor = '#10b981';
            } else if (avg >= 14) {
                result.innerHTML = `معدل: ${avg.toFixed(2)} <br> ✅ خوب`;
                result.style.color = '#3b82f6';
                result.style.borderColor = '#3b82f6';
            } else if (avg >= 10) {
                result.innerHTML = `معدل: ${avg.toFixed(2)} <br> ⚠️ قبول`;
                result.style.color = '#f59e0b';
                result.style.borderColor = '#f59e0b';
            } else {
                result.innerHTML = `معدل: ${avg.toFixed(2)} <br> ❌ مردود`;
                result.style.color = '#ef4444';
                result.style.borderColor = '#ef4444';
            }
        }

        // Unit Converter
        function convertUnit() {
            const type = document.getElementById('unitType').value;
            const input = parseFloat(document.getElementById('unitInput').value) || 0;
            const helper = parseFloat(document.getElementById('unitHelper').value) || 1;
            const result = document.getElementById('unitResult');
            
            let output = 0;
            let label = '';
            
            switch(type) {
                case 'v-a':
                    output = input / helper;
                    label = 'آمپر';
                    break;
                case 'w-v':
                    output = input / helper;
                    label = 'ولت';
                    break;
                case 'kw-w':
                    output = input * 1000;
                    label = 'وات';
                    break;
            }
            
            result.textContent = `${output.toFixed(2)} ${label}`;
        }

        // Color Picker
        function updateColor() {
            const color = document.getElementById('colorInput').value;
            document.getElementById('colorPreview').style.background = color;
            document.getElementById('colorCode').value = color;
        }

        function copyColor() {
            const code = document.getElementById('colorCode').value;
            navigator.clipboard.writeText(code).then(() => {
                showToast('کد رنگ کپی شد! ✅', 'success');
            });
        }

        // Code Editor
        function runCode() {
            const code = document.getElementById('codeInput').value;
            const output = document.getElementById('codeOutput');
            output.srcdoc = code;
            showToast('کد اجرا شد! 🚀', 'success');
        }

        // Accordion
        function toggleAccordion(header) {
            const body = header.nextElementSibling;
            const isActive = header.classList.contains('active');
            
            document.querySelectorAll('.accordion-header').forEach(h => h.classList.remove('active'));
            document.querySelectorAll('.accordion-body').forEach(b => b.classList.remove('active'));
            
            if (!isActive) {
                header.classList.add('active');
                body.classList.add('active');
            }
        }

        // Login System
        function openLoginModal() {
            document.getElementById('loginModal').classList.add('active');
        }

        function closeLoginModal() {
            document.getElementById('loginModal').classList.remove('active');
        }

        function checkLogin() {
            const username = document.getElementById('loginUsername').value;
            const password = document.getElementById('loginPassword').value;
            
            if (username === 'Hadisalkhori' && password === 'Hadisalkhori1234') {
                closeLoginModal();
                document.getElementById('mainContent').style.display = 'none';
                document.getElementById('teacherDashboard').classList.add('active');
                showToast('خوش آمدید جناب آقای سلخوری! 👨‍🏫', 'success');
                loadStudents();
            } else {
                showToast('نام کاربری یا رمز عبور اشتباه است! ❌', 'error');
            }
        }

        function logout() {
            document.getElementById('teacherDashboard').classList.remove('active');
            document.getElementById('mainContent').style.display = 'block';
            document.getElementById('loginUsername').value = '';
            document.getElementById('loginPassword').value = '';
            showToast('با موفقیت خارج شدید! 👋', 'success');
            window.scrollTo(0, 0);
        }

        // Student Management
        let students = JSON.parse(localStorage.getItem('students')) || [];

        function addStudent() {
            const name = document.getElementById('studentName').value.trim();
            const id = document.getElementById('studentId').value.trim();
            
            if (!name || !id) {
                showToast('لطفاً همه فیلدها را پر کنید! ⚠️', 'error');
                return;
            }
            
            const student = {
                id: Date.now(),
                name: name,
                studentId: id,
                date: new Date().toLocaleDateString('fa-IR')
            };
            
            students.push(student);
            localStorage.setItem('students', JSON.stringify(students));
            
            document.getElementById('studentName').value = '';
            document.getElementById('studentId').value = '';
            
            loadStudents();
            showToast('دانش‌آموز با موفقیت ثبت شد! ✅', 'success');
        }

        function loadStudents() {
            const container = document.getElementById('studentsListContainer');
            
            if (students.length === 0) {
                container.innerHTML = `
                    <div class="empty-state">
                        <i>👥</i>
                        <p>هنوز دانش‌آموزی ثبت نشده است</p>
                    </div>
                `;
                return;
            }
            
            container.innerHTML = students.map(student => `
                <div class="student-item">
                    <div>
                        <div class="student-name">${student.name}</div>
                        <div class="student-date">شماره دانش‌آموزی: ${student.studentId} | تاریخ ثبت: ${student.date}</div>
                    </div>
                    <button class="delete-btn" onclick="deleteStudent(${student.id})">🗑️ حذف</button>
                </div>
            `).join('');
        }

        function deleteStudent(id) {
            if (confirm('آیا از حذف این دانش‌آموز اطمینان دارید؟')) {
                students = students.filter(s => s.id !== id);
                localStorage.setItem('students', JSON.stringify(students));
                loadStudents();
                showToast('دانش‌آموز حذف شد! 🗑️', 'success');
            }
        }

        // Close modal on outside click
        document.getElementById('loginModal').addEventListener('click', function(e) {
            if (e.target === this) {
                closeLoginModal();
            }
        });

        // Enter key support for login
        document.getElementById('loginPassword').addEventListener('keypress', function(e) {
            if (e.key === 'Enter') {
                checkLogin();
            }
        });
    </script>
</body>
</html>
