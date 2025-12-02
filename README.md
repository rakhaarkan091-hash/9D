<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Science Quest - Petualangan Belajar IPA Kelas 9</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #4361ee;
            --secondary: #3a0ca3;
            --accent: #f72585;
            --success: #4cc9f0;
            --warning: #f8961e;
            --danger: #e63946;
            --light: #f8f9fa;
            --dark: #1a1a2e;
            --space: #0d1b2a;
            --neon: #00ff88;
            --gradient-primary: linear-gradient(135deg, #4361ee, #3a0ca3);
            --gradient-accent: linear-gradient(135deg, #f72585, #b5179e);
            --gradient-success: linear-gradient(135deg, #4cc9f0, #4895ef);
            --gradient-space: linear-gradient(135deg, #0d1b2a, #1a1a2e);
            --shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            --shadow-hover: 0 15px 40px rgba(0, 0, 0, 0.3);
            --border-radius: 16px;
            --transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: var(--gradient-space);
            color: var(--light);
            min-height: 100vh;
            position: relative;
            overflow-x: hidden;
        }
        
        /* Background dengan elemen sains */
        .science-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            opacity: 0.1;
        }
        
        .atom {
            position: absolute;
            width: 150px;
            height: 150px;
            border-radius: 50%;
            border: 2px dashed rgba(67, 97, 238, 0.3);
            animation: spin 20s linear infinite;
        }
        
        .atom:nth-child(1) {
            top: 10%;
            left: 10%;
            width: 100px;
            height: 100px;
            animation-duration: 25s;
        }
        
        .atom:nth-child(2) {
            top: 70%;
            right: 15%;
            width: 200px;
            height: 200px;
            animation-direction: reverse;
            animation-duration: 30s;
        }
        
        .atom:nth-child(3) {
            bottom: 20%;
            left: 20%;
            width: 120px;
            height: 120px;
            animation-duration: 22s;
        }
        
        .particle {
            position: absolute;
            width: 10px;
            height: 10px;
            background: var(--neon);
            border-radius: 50%;
            box-shadow: 0 0 15px var(--neon);
        }
        
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
            z-index: 1;
            position: relative;
        }
        
        /* Header dengan efek glassmorphism */
        header {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: var(--border-radius);
            padding: 25px 40px;
            margin-bottom: 30px;
            box-shadow: var(--shadow);
            border: 1px solid rgba(255, 255, 255, 0.1);
            position: relative;
            overflow: hidden;
        }
        
        header::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
            background: var(--gradient-accent);
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 20px;
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .logo-icon {
            background: var(--gradient-primary);
            width: 60px;
            height: 60px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 28px;
            box-shadow: 0 5px 15px rgba(67, 97, 238, 0.4);
        }
        
        .logo-text h1 {
            font-size: 2.2rem;
            background: linear-gradient(to right, #f72585, #4cc9f0);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            font-weight: 800;
            letter-spacing: 1px;
        }
        
        .logo-text p {
            color: rgba(255, 255, 255, 0.7);
            font-size: 0.9rem;
            letter-spacing: 1px;
        }
        
        .player-info {
            display: flex;
            gap: 20px;
            align-items: center;
        }
        
        .player-avatar {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: var(--gradient-success);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 22px;
            box-shadow: 0 5px 15px rgba(76, 201, 240, 0.4);
        }
        
        /* Dashboard dengan kartu statistik */
        .dashboard {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 25px;
            margin-bottom: 30px;
        }
        
        .stat-card {
            background: rgba(255, 255, 255, 0.08);
            backdrop-filter: blur(10px);
            border-radius: var(--border-radius);
            padding: 25px;
            box-shadow: var(--shadow);
            border: 1px solid rgba(255, 255, 255, 0.05);
            transition: var(--transition);
            position: relative;
            overflow: hidden;
        }
        
        .stat-card:hover {
            transform: translateY(-10px);
            box-shadow: var(--shadow-hover);
            border-color: rgba(76, 201, 240, 0.3);
        }
        
        .stat-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
            background: var(--gradient-primary);
        }
        
        .stat-card:nth-child(2)::before {
            background: var(--gradient-accent);
        }
        
        .stat-card:nth-child(3)::before {
            background: var(--gradient-success);
        }
        
        .stat-card:nth-child(4)::before {
            background: linear-gradient(135deg, #f8961e, #f3722c);
        }
        
        .stat-value {
            font-size: 3.5rem;
            font-weight: 800;
            margin-bottom: 10px;
            display: flex;
            align-items: baseline;
        }
        
        .stat-card:nth-child(1) .stat-value {
            color: #4361ee;
        }
        
        .stat-card:nth-child(2) .stat-value {
            color: #f72585;
        }
        
        .stat-card:nth-child(3) .stat-value {
            color: #4cc9f0;
        }
        
        .stat-card:nth-child(4) .stat-value {
            color: #f8961e;
        }
        
        .stat-label {
            font-size: 1rem;
            color: rgba(255, 255, 255, 0.7);
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .stat-icon {
            width: 40px;
            height: 40px;
            border-radius: 10px;
            background: rgba(67, 97, 238, 0.2);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 20px;
        }
        
        .stat-card:nth-child(1) .stat-icon {
            background: rgba(67, 97, 238, 0.2);
            color: #4361ee;
        }
        
        .stat-card:nth-child(2) .stat-icon {
            background: rgba(247, 37, 133, 0.2);
            color: #f72585;
        }
        
        .stat-card:nth-child(3) .stat-icon {
            background: rgba(76, 201, 240, 0.2);
            color: #4cc9f0;
        }
        
        .stat-card:nth-child(4) .stat-icon {
            background: rgba(248, 150, 30, 0.2);
            color: #f8961e;
        }
        
        /* Kontainer utama */
        .main-container {
            display: flex;
            gap: 30px;
            margin-bottom: 30px;
        }
        
        .content-area {
            flex: 3;
            background: rgba(255, 255, 255, 0.08);
            backdrop-filter: blur(10px);
            border-radius: var(--border-radius);
            padding: 30px;
            box-shadow: var(--shadow);
            border: 1px solid rgba(255, 255, 255, 0.05);
        }
        
        .sidebar {
            flex: 1;
            background: rgba(255, 255, 255, 0.08);
            backdrop-filter: blur(10px);
            border-radius: var(--border-radius);
            padding: 25px;
            box-shadow: var(--shadow);
            border: 1px solid rgba(255, 255, 255, 0.05);
            min-width: 300px;
        }
        
        /* Tampilan layar mulai */
        .start-screen {
            text-align: center;
            padding: 40px 20px;
        }
        
        .start-title {
            font-size: 3rem;
            margin-bottom: 20px;
            background: linear-gradient(to right, #f72585, #4cc9f0);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            font-weight: 800;
        }
        
        .start-subtitle {
            font-size: 1.2rem;
            color: rgba(255, 255, 255, 0.8);
            max-width: 700px;
            margin: 0 auto 40px;
            line-height: 1.6;
        }
        
        .materi-list {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin: 40px 0;
        }
        
        .materi-card {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 12px;
            padding: 20px;
            text-align: center;
            transition: var(--transition);
            border: 1px solid rgba(255, 255, 255, 0.05);
        }
        
        .materi-card:hover {
            background: rgba(67, 97, 238, 0.2);
            transform: translateY(-5px);
            border-color: rgba(67, 97, 238, 0.3);
        }
        
        .materi-icon {
            font-size: 2.5rem;
            margin-bottom: 15px;
            color: #4cc9f0;
        }
        
        .materi-card h4 {
            margin-bottom: 10px;
            font-size: 1.2rem;
        }
        
        .materi-card p {
            font-size: 0.9rem;
            color: rgba(255, 255, 255, 0.7);
        }
        
        /* Tombol dengan efek modern */
        .btn {
            padding: 16px 32px;
            border: none;
            border-radius: 12px;
            cursor: pointer;
            font-weight: 600;
            font-size: 1.1rem;
            transition: var(--transition);
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            position: relative;
            overflow: hidden;
        }
        
        .btn::after {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 5px;
            height: 5px;
            background: rgba(255, 255, 255, 0.5);
            opacity: 0;
            border-radius: 100%;
            transform: scale(1, 1) translate(-50%);
            transform-origin: 50% 50%;
        }
        
        .btn:focus:not(:active)::after {
            animation: ripple 1s ease-out;
        }
        
        @keyframes ripple {
            0% {
                transform: scale(0, 0);
                opacity: 0.5;
            }
            100% {
                transform: scale(20, 20);
                opacity: 0;
            }
        }
        
        .btn-primary {
            background: var(--gradient-primary);
            color: white;
            box-shadow: 0 5px 20px rgba(67, 97, 238, 0.4);
        }
        
        .btn-primary:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(67, 97, 238, 0.6);
        }
        
        .btn-accent {
            background: var(--gradient-accent);
            color: white;
            box-shadow: 0 5px 20px rgba(247, 37, 133, 0.4);
        }
        
        .btn-accent:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(247, 37, 133, 0.6);
        }
        
        .btn-success {
            background: var(--gradient-success);
            color: white;
            box-shadow: 0 5px 20px rgba(76, 201, 240, 0.4);
        }
        
        .btn-success:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(76, 201, 240, 0.6);
        }
        
        .btn-warning {
            background: linear-gradient(135deg, #f8961e, #f3722c);
            color: white;
            box-shadow: 0 5px 20px rgba(248, 150, 30, 0.4);
        }
        
        .btn-warning:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(248, 150, 30, 0.6);
        }
        
        .btn-lg {
            padding: 20px 40px;
            font-size: 1.3rem;
        }
        
        .btn-container {
            display: flex;
            gap: 20px;
            justify-content: center;
            flex-wrap: wrap;
            margin-top: 40px;
        }
        
        /* Tampilan soal */
        .question-container {
            display: none;
        }
        
        .question-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 30px;
            padding-bottom: 20px;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .question-meta {
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .question-badge {
            background: var(--gradient-primary);
            padding: 8px 16px;
            border-radius: 50px;
            font-weight: 600;
            font-size: 0.9rem;
            box-shadow: 0 3px 10px rgba(67, 97, 238, 0.3);
        }
        
        .question-number {
            font-size: 1.3rem;
            color: rgba(255, 255, 255, 0.9);
            font-weight: 600;
        }
        
        .question-progress {
            flex: 1;
            margin: 0 30px;
        }
        
        .progress-text {
            display: flex;
            justify-content: space-between;
            margin-bottom: 10px;
            font-size: 0.9rem;
            color: rgba(255, 255, 255, 0.7);
        }
        
        .progress-bar {
            height: 10px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 5px;
            overflow: hidden;
        }
        
        .progress-fill {
            height: 100%;
            background: var(--gradient-success);
            width: 0%;
            border-radius: 5px;
            transition: width 0.5s ease;
            position: relative;
            overflow: hidden;
        }
        
        .progress-fill::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
            animation: shimmer 2s infinite;
        }
        
        @keyframes shimmer {
            0% { transform: translateX(-100%); }
            100% { transform: translateX(100%); }
        }
        
        .question-text {
            font-size: 1.5rem;
            line-height: 1.6;
            margin-bottom: 40px;
            padding: 20px;
            background: rgba(255, 255, 255, 0.05);
            border-radius: var(--border-radius);
            border-left: 5px solid #4361ee;
        }
        
        .options-container {
            display: grid;
            grid-template-columns: 1fr;
            gap: 15px;
            margin-bottom: 30px;
        }
        
        .option {
            padding: 20px;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 12px;
            cursor: pointer;
            transition: var(--transition);
            border: 2px solid transparent;
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .option:hover {
            background: rgba(67, 97, 238, 0.1);
            transform: translateX(10px);
        }
        
        .option.selected {
            background: rgba(67, 97, 238, 0.2);
            border-color: #4361ee;
            box-shadow: 0 5px 15px rgba(67, 97, 238, 0.2);
        }
        
        .option.correct {
            background: rgba(76, 201, 240, 0.2);
            border-color: #4cc9f0;
        }
        
        .option.incorrect {
            background: rgba(247, 37, 133, 0.2);
            border-color: #f72585;
        }
        
        .option-letter {
            width: 40px;
            height: 40px;
            border-radius: 10px;
            background: rgba(255, 255, 255, 0.1);
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            flex-shrink: 0;
        }
        
        .option.selected .option-letter {
            background: #4361ee;
            color: white;
        }
        
        .option.correct .option-letter {
            background: #4cc9f0;
            color: white;
        }
        
        .option.incorrect .option-letter {
            background: #f72585;
            color: white;
        }
        
        .navigation {
            display: flex;
            justify-content: space-between;
            margin-top: 40px;
        }
        
        .explanation {
            margin-top: 30px;
            padding: 25px;
            background: rgba(26, 26, 46, 0.8);
            border-radius: var(--border-radius);
            border-left: 5px solid #f8961e;
            display: none;
        }
        
        .explanation h4 {
            color: #f8961e;
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        /* Tampilan hasil */
        .result-container {
            display: none;
            text-align: center;
            padding: 40px 20px;
        }
        
        .result-title {
            font-size: 3rem;
            margin-bottom: 20px;
            background: linear-gradient(to right, #f72585, #4cc9f0);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            font-weight: 800;
        }
        
        .score-display {
            font-size: 6rem;
            font-weight: 800;
            margin: 30px 0;
            position: relative;
            display: inline-block;
        }
        
        .score-value {
            background: linear-gradient(to right, #f72585, #4cc9f0, #00ff88);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            text-shadow: 0 5px 20px rgba(0, 0, 0, 0.3);
        }
        
        .score-circle {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: transl
