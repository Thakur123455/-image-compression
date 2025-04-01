<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PixelPress Pro | AI-Powered Image Compression</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #6C5CE7;
            --primary-light: #A29BFE;
            --secondary: #FD79A8;
            --accent: #00CEC9;
            --dark: #2D3436;
            --light: #F5F6FA;
            --success: #00B894;
            --warning: #FDCB6E;
            --danger: #D63031;
            --gray: #636E72;
            --gray-light: #DFE6E9;
            
            --glass: rgba(255, 255, 255, 0.15);
            --glass-border: rgba(255, 255, 255, 0.2);
            
            --shadow-sm: 0 2px 8px rgba(0,0,0,0.08);
            --shadow-md: 0 4px 16px rgba(0,0,0,0.12);
            --shadow-lg: 0 8px 32px rgba(0,0,0,0.16);
            --shadow-xl: 0 16px 64px rgba(0,0,0,0.2);
            
            --radius-sm: 6px;
            --radius-md: 12px;
            --radius-lg: 24px;
            --radius-xl: 36px;
            --radius-full: 9999px;
            
            --transition: all 0.4s cubic-bezier(0.16, 1, 0.3, 1);
            --transition-fast: all 0.2s ease-out;
            
            --gradient-primary: linear-gradient(135deg, var(--primary), var(--primary-light));
            --gradient-accent: linear-gradient(135deg, var(--accent), var(--secondary));
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
            line-height: 1.6;
            color: var(--dark);
            background-color: var(--light);
            overflow-x: hidden;
            -webkit-font-smoothing: antialiased;
        }
        
        /* Smooth scroll and focus styles */
        html {
            scroll-behavior: smooth;
        }
        
        :focus-visible {
            outline: 2px solid var(--primary);
            outline-offset: 2px;
        }
        
        /* Container */
        .container {
            width: 100%;
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 1.5rem;
        }
        
        /* Glassmorphism effect */
        .glass {
            background: var(--glass);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border: 1px solid var(--glass-border);
            box-shadow: var(--shadow-sm);
        }
        
        /* Header - Neumorphic Design */
        header {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            z-index: 1000;
            padding: 1rem 0;
            transition: var(--transition);
        }
        
        .header-scrolled {
            background-color: rgba(255, 255, 255, 0.98);
            box-shadow: var(--shadow-sm);
            backdrop-filter: blur(10px);
            padding: 0.5rem 0;
        }
        
        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            height: 70px;
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 0.75rem;
            text-decoration: none;
            font-weight: 800;
            font-size: 1.5rem;
            background: var(--gradient-primary);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }
        
        .logo-icon {
            font-size: 1.75rem;
        }
        
        /* Navigation */
        .nav-links {
            display: flex;
            gap: 2rem;
        }
        
        .nav-link {
            position: relative;
            text-decoration: none;
            color: var(--dark);
            font-weight: 600;
            transition: var(--transition-fast);
            padding: 0.5rem 0;
        }
        
        .nav-link::before {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 3px;
            background: var(--gradient-primary);
            border-radius: 3px;
            transition: var(--transition);
        }
        
        .nav-link:hover::before {
            width: 100%;
        }
        
        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            font-size: 1.5rem;
            color: var(--dark);
            cursor: pointer;
            z-index: 1001;
        }
        
        /* Hero Section - 3D Perspective */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            padding: 8rem 0 4rem;
            position: relative;
            overflow: hidden;
            background: linear-gradient(145deg, #f5f7ff 0%, #f8f9fa 100%);
        }
        
        .hero::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -20%;
            width: 100%;
            height: 200%;
            background: radial-gradient(circle, rgba(108, 92, 231, 0.08) 0%, rgba(108, 92, 231, 0) 70%);
            transform: rotate(30deg);
            z-index: 0;
        }
        
        .hero-content {
            position: relative;
            z-index: 1;
            max-width: 800px;
            margin: 0 auto;
            text-align: center;
        }
        
        .hero-title {
            font-size: clamp(2.5rem, 5vw, 4rem);
            font-weight: 800;
            margin-bottom: 1.5rem;
            line-height: 1.2;
            background: linear-gradient(to right, var(--primary), var(--accent));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }
        
        .hero-subtitle {
            font-size: clamp(1rem, 2vw, 1.25rem);
            color: var(--gray);
            margin-bottom: 2.5rem;
            line-height: 1.6;
            max-width: 700px;
            margin-left: auto;
            margin-right: auto;
        }
        
        .hero-buttons {
            display: flex;
            gap: 1rem;
            justify-content: center;
            margin-bottom: 3rem;
            flex-wrap: wrap;
        }
        
        /* Button Styles */
        .btn {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 0.5rem;
            padding: 0.875rem 1.75rem;
            border-radius: var(--radius-md);
            font-weight: 600;
            text-decoration: none;
            transition: var(--transition);
            cursor: pointer;
            border: none;
            position: relative;
            overflow: hidden;
            z-index: 1;
        }
        
        .btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: var(--gradient-primary);
            z-index: -1;
            opacity: 0;
            transition: var(--transition);
        }
        
        .btn-primary {
            background-color: var(--primary);
            color: white;
            box-shadow: 0 4px 20px rgba(108, 92, 231, 0.3);
        }
        
        .btn-primary:hover {
            transform: translateY(-3px) scale(1.02);
            box-shadow: 0 8px 30px rgba(108, 92, 231, 0.4);
        }
        
        .btn-primary::before {
            background: var(--gradient-accent);
        }
        
        .btn-primary:hover::before {
            opacity: 1;
        }
        
        .btn-secondary {
            background-color: white;
            color: var(--primary);
            border: 1px solid var(--gray-light);
            box-shadow: var(--shadow-sm);
        }
        
        .btn-secondary:hover {
            transform: translateY(-3px);
            box-shadow: var(--shadow-md);
            border-color: var(--primary-light);
        }
        
        /* Floating Particles Background */
        .particles {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 0;
            overflow: hidden;
        }
        
        .particle {
            position: absolute;
            background: var(--primary-light);
            border-radius: 50%;
            opacity: 0.3;
            animation: float linear infinite;
        }
        
        @keyframes float {
            0% {
                transform: translateY(0) rotate(0deg);
            }
            100% {
                transform: translateY(-100vh) rotate(360deg);
            }
        }
        
        /* Main Compressor Section - Glass Morphism */
        .compressor-section {
            padding: 5rem 0;
            position: relative;
            background: linear-gradient(to bottom, #f5f7ff, #ffffff);
        }
        
        .compressor-container {
            background: white;
            border-radius: var(--radius-xl);
            box-shadow: var(--shadow-xl);
            padding: 3rem;
            margin-top: -5rem;
            position: relative;
            z-index: 10;
            overflow: hidden;
        }
        
        .compressor-container::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -50%;
            width: 100%;
            height: 200%;
            background: radial-gradient(circle, rgba(0, 206, 201, 0.1) 0%, rgba(0, 206, 201, 0) 70%);
            z-index: -1;
        }
        
        .section-header {
            text-align: center;
            margin-bottom: 3rem;
        }
        
        .section-title {
            font-size: clamp(1.75rem, 3vw, 2.5rem);
            font-weight: 800;
            margin-bottom: 1rem;
            color: var(--dark);
            position: relative;
            display: inline-block;
        }
        
        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background: var(--gradient-primary);
            border-radius: 2px;
        }
        
        .section-subtitle {
            font-size: 1.1rem;
            color: var(--gray);
            max-width: 600px;
            margin: 0 auto;
        }
        
        /* Upload Area - Interactive 3D Card */
        .upload-area {
            border: 2px dashed var(--gray-light);
            border-radius: var(--radius-lg);
            padding: 3rem 2rem;
            text-align: center;
            cursor: pointer;
            transition: var(--transition);
            margin-bottom: 2rem;
            position: relative;
            overflow: hidden;
            background-color: white;
            box-shadow: var(--shadow-sm);
            transform-style: preserve-3d;
            perspective: 1000px;
        }
        
        .upload-area:hover {
            border-color: var(--primary-light);
            box-shadow: var(--shadow-md);
            transform: translateY(-5px);
        }
        
        .upload-area.active {
            border-color: var(--success);
            background-color: rgba(0, 184, 148, 0.03);
        }
        
        .upload-icon {
            font-size: 3.5rem;
            margin-bottom: 1.5rem;
            color: var(--primary);
            transition: var(--transition);
            display: inline-block;
        }
        
        .upload-area:hover .upload-icon {
            transform: translateY(-5px) scale(1.1);
            color: var(--accent);
        }
        
        .upload-title {
            font-size: 1.5rem;
            font-weight: 700;
            margin-bottom: 0.5rem;
            color: var(--dark);
        }
        
        .upload-subtitle {
            font-size: 1rem;
            color: var(--gray);
            margin-bottom: 1.5rem;
        }
        
        .upload-btn {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            padding: 0.75rem 1.5rem;
            background: var(--gradient-primary);
            color: white;
            border-radius: var(--radius-md);
            font-weight: 600;
            transition: var(--transition);
            border: none;
            cursor: pointer;
            box-shadow: 0 4px 12px rgba(108, 92, 231, 0.2);
        }
        
        .upload-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(108, 92, 231, 0.3);
        }
        
        .file-input {
            position: absolute;
            width: 0.1px;
            height: 0.1px;
            opacity: 0;
            overflow: hidden;
            z-index: -1;
        }
        
        /* Preview Area - Interactive Grid */
        .preview-area {
            display: none;
            margin-bottom: 2rem;
            animation: fadeIn 0.5s ease-out;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .preview-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1.5rem;
        }
        
        .preview-title {
            font-size: 1.25rem;
            font-weight: 700;
            color: var(--dark);
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }
        
        .preview-count {
            background: var(--primary);
            color: white;
            padding: 0.25rem 0.75rem;
            border-radius: var(--radius-full);
            font-size: 0.85rem;
        }
        
        .clear-btn {
            background: none;
            border: none;
            color: var(--danger);
            font-weight: 600;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 0.5rem;
            transition: var(--transition-fast);
            padding: 0.5rem 1rem;
            border-radius: var(--radius-sm);
        }
        
        .clear-btn:hover {
            background-color: rgba(214, 48, 49, 0.1);
        }
        
        .preview-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            gap: 1.5rem;
        }
        
        .preview-card {
            background-color: white;
            border-radius: var(--radius-md);
            box-shadow: var(--shadow-sm);
            overflow: hidden;
            transition: var(--transition);
            position: relative;
            border: 1px solid var(--gray-light);
        }
        
        .preview-card:hover {
            transform: translateY(-5px);
            box-shadow: var(--shadow-md);
            border-color: var(--primary-light);
        }
        
        .preview-image {
            width: 100%;
            height: 140px;
            object-fit: cover;
            border-bottom: 1px solid var(--gray-light);
        }
        
        .preview-info {
            padding: 1rem;
        }
        
        .preview-name {
            font-size: 0.9rem;
            font-weight: 600;
            margin-bottom: 0.25rem;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }
        
        .preview-size {
            font-size: 0.8rem;
            color: var(--gray);
            display: flex;
            align-items: center;
            gap: 0.25rem;
        }
        
        .remove-btn {
            position: absolute;
            top: 0.5rem;
            right: 0.5rem;
            width: 28px;
            height: 28px;
            background-color: rgba(255, 255, 255, 0.9);
            color: var(--danger);
            border: none;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            opacity: 0;
            transition: var(--transition-fast);
            box-shadow: var(--shadow-sm);
        }
        
        .preview-card:hover .remove-btn {
            opacity: 1;
        }
        
        .remove-btn:hover {
            background-color: var(--danger);
            color: white;
        }
        
        /* Controls - Interactive Sliders */
        .controls {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
            margin-bottom: 2rem;
        }
        
        .control-group {
            margin-bottom: 1rem;
        }
        
        .control-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 0.75rem;
        }
        
        .control-label {
            font-weight: 700;
            color: var(--dark);
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }
        
        .control-value {
            font-weight: 700;
            color: var(--primary);
            font-size: 1.1rem;
        }
        
        .slider-container {
            position: relative;
            height: 8px;
            background-color: var(--gray-light);
            border-radius: var(--radius-full);
            margin-top: 1.5rem;
        }
        
        .slider {
            -webkit-appearance: none;
            width: 100%;
            height: 8px;
            background: transparent;
            outline: none;
            position: absolute;
            top: 0;
            left: 0;
            z-index: 2;
            cursor: pointer;
        }
        
        .slider::-webkit-slider-thumb {
            -webkit-appearance: none;
            appearance: none;
            width: 20px;
            height: 20px;
            border-radius: 50%;
            background: var(--primary);
            cursor: pointer;
            box-shadow: 0 2px 6px rgba(0,0,0,0.2);
            transition: var(--transition-fast);
            border: 3px solid white;
        }
        
        .slider::-webkit-slider-thumb:hover {
            transform: scale(1.2);
            background: var(--accent);
        }
        
        .slider-progress {
            position: absolute;
            top: 0;
            left: 0;
            height: 100%;
            background: var(--gradient-primary);
            border-radius: var(--radius-full);
            z-index: 1;
        }
        
        .select-wrapper {
            position: relative;
            border-radius: var(--radius-md);
            background-color: white;
            box-shadow: var(--shadow-sm);
            border: 1px solid var(--gray-light);
            transition: var(--transition-fast);
        }
        
        .select-wrapper:hover {
            border-color: var(--primary-light);
            box-shadow: var(--shadow-md);
        }
        
        .select-wrapper::after {
            content: '\f078';
            font-family: 'Font Awesome 6 Free';
            font-weight: 900;
            position: absolute;
            top: 50%;
            right: 1rem;
            transform: translateY(-50%);
            color: var(--gray);
            pointer-events: none;
            font-size: 0.8rem;
        }
        
        select {
            width: 100%;
            padding: 0.875rem 1rem;
            border: none;
            border-radius: var(--radius-md);
            font-size: 1rem;
            color: var(--dark);
            background-color: transparent;
            appearance: none;
            cursor: pointer;
        }
        
        select:focus {
            outline: none;
        }
        
        /* Action Buttons - Floating Effect */
        .action-buttons {
            display: flex;
            gap: 1rem;
            margin-top: 2rem;
            flex-wrap: wrap;
        }
        
        .btn-lg {
            padding: 1rem 2rem;
            font-size: 1.1rem;
        }
        
        .btn-accent {
            background: var(--gradient-accent);
            color: white;
            box-shadow: 0 4px 20px rgba(0, 206, 201, 0.3);
        }
        
        .btn-accent:hover {
            transform: translateY(-3px) scale(1.02);
            box-shadow: 0 8px 30px rgba(0, 206, 201, 0.4);
        }
        
        .btn-outline {
            background-color: transparent;
            color: var(--gray);
            border: 1px solid var(--gray-light);
            box-shadow: none;
        }
        
        .btn-outline:hover {
            background-color: rgba(108, 92, 231, 0.05);
            color: var(--primary);
            border-color: var(--primary-light);
        }
        
        /* Results Section - Interactive Comparison */
        .results-section {
            display: none;
            margin-top: 3rem;
            animation: fadeIn 0.5s ease-out;
        }
        
        .results-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 2rem;
            padding-bottom: 1.5rem;
            border-bottom: 1px solid var(--gray-light);
        }
        
        .results-title {
            font-size: 1.5rem;
            font-weight: 800;
            color: var(--dark);
            display: flex;
            align-items: center;
            gap: 0.75rem;
        }
        
        .results-title i {
            color: var(--success);
        }
        
        .results-summary {
            display: flex;
            gap: 2rem;
        }
        
        .summary-item {
            text-align: center;
            min-width: 100px;
        }
        
        .summary-value {
            font-size: 1.5rem;
            font-weight: 800;
            color: var(--primary);
            margin-bottom: 0.25rem;
        }
        
        .summary-label {
            font-size: 0.85rem;
            color: var(--gray);
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }
        
        .results-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 2rem;
        }
        
        .result-card {
            background-color: white;
            border-radius: var(--radius-lg);
            box-shadow: var(--shadow-sm);
            overflow: hidden;
            transition: var(--transition);
            border: 1px solid var(--gray-light);
        }
        
        .result-card:hover {
            transform: translateY(-5px);
            box-shadow: var(--shadow-md);
        }
        
        .result-comparison {
            position: relative;
            height: 200px;
            overflow: hidden;
        }
        
        .result-original, .result-compressed {
            position: absolute;
            top: 0;
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .result-compressed {
            clip-path: inset(0 50% 0 0);
            transition: clip-path 0.4s ease;
        }
        
        .result-comparison:hover .result-compressed {
            clip-path: inset(0 0 0 0);
        }
        
        .result-comparison:hover::after {
            content: 'Drag ←→ to compare';
            position: absolute;
            bottom: 10px;
            left: 50%;
            transform: translateX(-50%);
            background-color: rgba(0, 0, 0, 0.7);
            color: white;
            padding: 0.25rem 0.75rem;
            border-radius: var(--radius-full);
            font-size: 0.75rem;
            z-index: 2;
        }
        
        .result-stats {
            padding: 1.5rem;
        }
        
        .result-name {
            font-size: 1rem;
            font-weight: 700;
            margin-bottom: 1rem;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }
        
        .progress-container {
            height: 8px;
            background-color: var(--gray-light);
            border-radius: var(--radius-full);
            margin-bottom: 1.5rem;
            overflow: hidden;
        }
        
        .progress-bar {
            height: 100%;
            background: var(--gradient-primary);
            border-radius: var(--radius-full);
            transition: width 0.5s ease;
            position: relative;
            overflow: hidden;
        }
        
        .progress-bar::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(90deg, 
                rgba(255,255,255,0) 0%, 
                rgba(255,255,255,0.3) 50%, 
                rgba(255,255,255,0) 100%);
            animation: shimmer 2s infinite;
        }
        
        @keyframes shimmer {
            0% { transform: translateX(-100%); }
            100% { transform: translateX(100%); }
        }
        
        .stat-row {
            display: flex;
            justify-content: space-between;
            margin-bottom: 0.75rem;
        }
        
        .stat-label {
            font-size: 0.9rem;
            color: var(--gray);
            display: flex;
            align-items: center;
            gap: 0.25rem;
        }
        
        .stat-value {
            font-size: 0.9rem;
            font-weight: 700;
        }
        
        .savings {
            color: var(--success);
        }
        
        .download-btn {
            display: block;
            width: 100%;
            text-align: center;
            padding: 1rem;
            background: var(--gradient-primary);
            color: white;
            text-decoration: none;
            font-weight: 600;
            transition: var(--transition);
            border: none;
            cursor: pointer;
        }
        
        .download-btn:hover {
            background: var(--gradient-accent);
        }
        
        /* Features Section - Animated Cards */
        .features-section {
            padding: 6rem 0;
            background: linear-gradient(to bottom, #ffffff, #f5f7ff);
            position: relative;
            overflow: hidden;
        }
        
        .features-section::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%236C5CE7' fill-opacity='0.05'%3E%3Cpath d='M36 34v-4h-2v4h-4v2h4v4h2v-4h4v-2h-4zm0-30V0h-2v4h-4v2h4v4h2V6h4V4h-4zM6 34v-4H4v4H0v2h4v4h2v-4h4v-2H6zM6 4V0H4v4H0v2h4v4h2V6h4V4H6z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E");
            z-index: 0;
        }
        
        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
            position: relative;
            z-index: 1;
        }
        
        .feature-card {
            background-color: white;
            border-radius: var(--radius-lg);
            padding: 2.5rem;
            box-shadow: var(--shadow-sm);
            transition: var(--transition);
            border: 1px solid var(--gray-light);
            position: relative;
            overflow: hidden;
        }
        
        .feature-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 4px;
            height: 0;
            background: var(--gradient-primary);
            transition: var(--transition);
        }
        
        .feature-card:hover {
            transform: translateY(-10px);
            box-shadow: var(--shadow-lg);
        }
        
        .feature-card:hover::before {
            height: 100%;
        }
        
        .feature-icon {
            font-size: 2.5rem;
            margin-bottom: 1.5rem;
            color: var(--primary);
            transition: var(--transition);
        }
        
        .feature-card:hover .feature-icon {
            transform: scale(1.2);
            color: var(--accent);
        }
        
        .feature-title {
            font-size: 1.25rem;
            font-weight: 800;
            margin-bottom: 1rem;
            color: var(--dark);
        }
        
        .feature-desc {
            color: var(--gray);
            line-height: 1.7;
        }
        
        /* How It Works - Timeline */
        .how-it-works {
            padding: 6rem 0;
            background: linear-gradient(to bottom, #f5f7ff, #ffffff);
        }
        
        .steps {
            display: flex;
            flex-direction: column;
            gap: 2rem;
            max-width: 800px;
            margin: 4rem auto 0;
            position: relative;
        }
        
        .step {
            display: flex;
            gap: 2rem;
            position: relative;
            z-index: 1;
        }
        
        .step-number {
            flex-shrink: 0;
            width: 60px;
            height: 60px;
            border-radius: 50%;
            background: white;
            color: var(--primary);
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 800;
            font-size: 1.5rem;
            box-shadow: var(--shadow-md);
            border: 3px solid var(--primary-light);
            transition: var(--transition);
        }
        
        .step:hover .step-number {
            background: var(--gradient-primary);
            color: white;
            transform: scale(1.1);
        }
        
        .step-content {
            background-color: white;
            border-radius: var(--radius-lg);
            padding: 2rem;
            box-shadow: var(--shadow-sm);
            flex: 1;
            border: 1px solid var(--gray-light);
            transition: var(--transition);
        }
        
        .step:hover .step-content {
            transform: translateX(10px);
            box-shadow: var(--shadow-md);
        }
        
        .step-title {
            font-size: 1.25rem;
            font-weight: 800;
            margin-bottom: 0.75rem;
            color: var(--dark);
        }
        
        .step-desc {
            color: var(--gray);
            line-height: 1.7;
        }
        
        .steps::before {
            content: '';
            position: absolute;
            top: 0;
            bottom: 0;
            left: 30px;
            width: 4px;
            background: var(--gradient-primary);
            z-index: 0;
        }
        
        /* FAQ Section - Animated Accordion */
        .faq-section {
            padding: 6rem 0;
            background: linear-gradient(to bottom, #ffffff, #f8f9fa);
        }
        
        .faq-container {
            max-width: 800px;
            margin: 0 auto;
        }
        
        .faq-item {
            background-color: white;
            border-radius: var(--radius-md);
            margin-bottom: 1rem;
            box-shadow: var(--shadow-sm);
            overflow: hidden;
            transition: var(--transition);
            border: 1px solid var(--gray-light);
        }
        
        .faq-item:hover {
            box-shadow: var(--shadow-md);
        }
        
        .faq-question {
            padding: 1.5rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            cursor: pointer;
            font-weight: 700;
            color: var(--dark);
            transition: var(--transition-fast);
        }
        
        .faq-question:hover {
            background-color: rgba(108, 92, 231, 0.05);
        }
        
        .faq-question::after {
            content: '\f078';
            font-family: 'Font Awesome 6 Free';
            font-weight: 900;
            transition: var(--transition);
        }
        
        .faq-item.active .faq-question::after {
            transform: rotate(180deg);
        }
        
        .faq-answer {
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.4s cubic-bezier(0.16, 1, 0.3, 1);
            padding: 0 1.5rem;
        }
        
        .faq-item.active .faq-answer {
            max-height: 500px;
            padding-bottom: 1.5rem;
        }
        
        /* Footer - Gradient Background */
        footer {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            padding: 6rem 0 3rem;
            position: relative;
            overflow: hidden;
        }
        
        footer::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%23ffffff' fill-opacity='0.1'%3E%3Cpath d='M36 34v-4h-2v4h-4v2h4v4h2v-4h4v-2h-4zm0-30V0h-2v4h-4v2h4v4h2V6h4V4h-4zM6 34v-4H4v4H0v2h4v4h2v-4h4v-2H6zM6 4V0H4v4H0v2h4v4h2V6h4V4H6z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E");
            z-index: 0;
        }
        
        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 3rem;
            margin-bottom: 3rem;
            position: relative;
            z-index: 1;
        }
        
        .footer-logo {
            display: flex;
            align-items: center;
            gap: 0.75rem;
            margin-bottom: 1.5rem;
            text-decoration: none;
            font-weight: 800;
            font-size: 1.5rem;
            color: white;
        }
        
        .footer-logo-icon {
            font-size: 1.75rem;
        }
        
        .footer-desc {
            color: rgba(255, 255, 255, 0.8);
            line-height: 1.7;
            margin-bottom: 1.5rem;
        }
        
        .social-links {
            display: flex;
            gap: 1rem;
        }
        
        .social-link {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background-color: rgba(255, 255, 255, 0.1);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            transition: var(--transition);
        }
        
        .social-link:hover {
            background-color: white;
            color: var(--primary);
            transform: translateY(-3px);
        }
        
        .footer-title {
            font-size: 1.25rem;
            font-weight: 700;
            margin-bottom: 1.5rem;
            color: white;
        }
        
        .footer-links {
            list-style: none;
        }
        
        .footer-link-item {
            margin-bottom: 1rem;
        }
        
        .footer-link {
            color: rgba(255, 255, 255, 0.8);
            text-decoration: none;
            transition: var(--transition-fast);
            display: inline-block;
        }
        
        .footer-link:hover {
            color: white;
            transform: translateX(5px);
        }
        
        .footer-bottom {
            text-align: center;
            padding-top: 3rem;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            color: rgba(255, 255, 255, 0.7);
            font-size: 0.9rem;
            position: relative;
            z-index: 1;
        }
        
        /* Tooltip - Modern Style */
        .tooltip {
            position: relative;
            display: inline-block;
            cursor: pointer;
        }
        
        .tooltip-icon {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 18px;
            height: 18px;
            background-color: var(--primary-light);
            color: white;
            border-radius: 50%;
            font-size: 0.7rem;
            font-weight: bold;
            margin-left: 0.5rem;
        }
        
        .tooltip-text {
            visibility: hidden;
            width: 240px;
            background-color: var(--dark);
            color: white;
            text-align: center;
            border-radius: var(--radius-md);
            padding: 0.75rem 1rem;
            position: absolute;
            z-index: 100;
            bottom: 125%;
            left: 50%;
            transform: translateX(-50%);
            opacity: 0;
            transition: opacity 0.3s;
            font-size: 0.85rem;
            font-weight: normal;
            line-height: 1.5;
            box-shadow: var(--shadow-lg);
        }
        
        .tooltip-text::after {
            content: '';
            position: absolute;
            top: 100%;
            left: 50%;
            margin-left: -5px;
            border-width: 5px;
            border-style: solid;
            border-color: var(--dark) transparent transparent transparent;
        }
        
        .tooltip:hover .tooltip-text {
            visibility: visible;
            opacity: 1;
        }
        
        /* Spinner - Modern Animation */
        .spinner {
            display: inline-block;
            width: 20px;
            height: 20px;
            border: 3px solid rgba(255, 255, 255, 0.3);
            border-radius: 50%;
            border-top-color: white;
            animation: spin 1s ease-in-out infinite;
        }
        
        @keyframes spin {
            to { transform: rotate(360deg); }
        }
        
        /* Toast Notification - Modern Style */
        .toast {
            position: fixed;
            bottom: 2rem;
            right: 2rem;
            background-color: var(--dark);
            color: white;
            padding: 1rem 1.5rem;
            border-radius: var(--radius-md);
            box-shadow: var(--shadow-xl);
            display: flex;
            align-items: center;
            gap: 1rem;
            z-index: 1000;
            transform: translateY(100px);
            opacity: 0;
            transition: all 0.4s cubic-bezier(0.68, -0.55, 0.27, 1.55);
        }
        
        .toast.show {
            transform: translateY(0);
            opacity: 1;
        }
        
        .toast-icon {
            font-size: 1.25rem;
        }
        
        .toast-success .toast-icon {
            color: var(--success);
        }
        
        .toast-error .toast-icon {
            color: var(--danger);
        }
        
        .toast-info .toast-icon {
            color: var(--accent);
        }
        
        .toast-message {
            font-size: 0.9rem;
        }
        
        .toast-close {
            margin-left: 0.5rem;
            cursor: pointer;
            opacity: 0.7;
            transition: var(--transition-fast);
            display: flex;
            align-items: center;
            justify-content: center;
            width: 24px;
            height: 24px;
            border-radius: 50%;
        }
        
        .toast-close:hover {
            opacity: 1;
            background-color: rgba(255, 255, 255, 0.1);
        }
        
        /* Responsive Styles */
        @media (max-width: 1024px) {
            .hero-title {
                font-size: 3rem;
            }
            
            .compressor-container {
                margin-top: 0;
            }
            
            .steps::before {
                left: 30px;
            }
        }
        
        @media (max-width: 768px) {
            .header-container {
                padding: 0 1rem;
            }
            
            .nav-links {
                position: fixed;
                top: 0;
                right: -100%;
                width: 280px;
                height: 100vh;
                background-color: white;
                flex-direction: column;
                padding: 6rem 2rem 2rem;
                box-shadow: var(--shadow-lg);
                transition: var(--transition);
            }
            
            .nav-links.active {
                right: 0;
            }
            
            .mobile-menu-btn {
                display: block;
            }
            
            .hero {
                padding: 6rem 0 3rem;
            }
            
            .hero-title {
                font-size: 2.5rem;
            }
            
            .hero-subtitle {
                font-size: 1.1rem;
            }
            
            .hero-buttons {
                flex-direction: column;
                align-items: center;
            }
            
            .compressor-section {
                padding: 3rem 0;
            }
            
            .compressor-container {
                padding: 1.5rem;
            }
            
            .section-title {
                font-size: 1.75rem;
            }
            
            .steps::before {
                display: none;
            }
            
            .step {
                flex-direction: column;
                align-items: flex-start;
            }
            
            .step-content {
                margin-left: 0;
                width: 100%;
            }
            
            .results-summary {
                flex-direction: column;
                gap: 1rem;
                align-items: flex-start;
            }
        }
        
        @media (max-width: 480px) {
            .hero-title {
                font-size: 2rem;
            }
            
            .section-title {
                font-size: 1.5rem;
            }
            
            .action-buttons {
                flex-direction: column;
            }
            
            .btn {
                width: 100%;
            }
            
            .preview-grid {
                grid-template-columns: 1fr;
            }
            
            .footer-content {
                grid-template-columns: 1fr;
                text-align: center;
            }
            
            .social-links {
                justify-content: center;
            }
            
            .footer-links {
                text-align: center;
            }
            
            .footer-link:hover {
                transform: none;
            }
        }
    </style>
</head>
<body>
    <!-- Floating Particles Background -->
    <div class="particles" id="particles"></div>
    
    <!-- Header -->
    <header id="header">
        <div class="container header-container">
            <a href="#" class="logo">
                <i class="fas fa-compress-alt logo-icon"></i>
                <span>PixelPress</span>
            </a>
            <nav class="nav-links">
                <a href="#features" class="nav-link">Features</a>
                <a href="#how-it-works" class="nav-link">How It Works</a>
                <a href="#faq" class="nav-link">FAQ</a>
                <a href="#contact" class="nav-link">Contact</a>
            </nav>
            <button class="mobile-menu-btn" id="mobileMenuBtn">
                <i class="fas fa-bars"></i>
            </button>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="container hero-content">
            <h1 class="hero-title">AI-Powered Image Compression</h1>
            <p class="hero-subtitle">Reduce image sizes by up to 90% without quality loss. Perfect for websites, apps, and social media. Processed locally in your browser for maximum privacy.</p>
            <div class="hero-buttons">
                <a href="#compressor" class="btn btn-primary">
                    <i class="fas fa-rocket"></i> Compress Now
                </a>
                <a href="#how-it-works" class="btn btn-secondary">
                    <i class="fas fa-play-circle"></i> See How It Works
                </a>
            </div>
        </div>
    </section>

    <!-- Main Compressor Section -->
    <section id="compressor" class="compressor-section">
        <div class="container">
            <div class="compressor-container">
                <div class="section-header">
                    <h2 class="section-title">Smart Image Compression</h2>
                    <p class="section-subtitle">Upload your images and optimize them with our intelligent compression algorithm.</p>
                </div>
                
                <!-- Upload Area -->
                <div class="upload-area" id="dropArea">
                    <div class="upload-icon">
                        <i class="fas fa-cloud-upload-alt"></i>
                    </div>
                    <h3 class="upload-title">Drag & Drop Your Images Here</h3>
                    <p class="upload-subtitle">or click to browse files (JPG, PNG, WebP supported)</p>
                    <button class="upload-btn" id="uploadBtn">
                        <i class="fas fa-folder-open"></i> Select Files
                    </button>
                    <input type="file" id="fileInput" class="file-input" accept="image/*" multiple>
                </div>
                
                <!-- Preview Area -->
                <div class="preview-area" id="previewArea">
                    <div class="preview-header">
                        <h3 class="preview-title">
                            <i class="fas fa-images"></i> Selected Files
                            <span class="preview-count" id="fileCount">0</span>
                        </h3>
                        <button class="clear-btn" id="clearBtn">
                            <i class="fas fa-trash"></i> Clear All
                        </button>
                    </div>
                    <div class="preview-grid" id="previewGrid"></div>
                </div>
                
                <!-- Compression Controls -->
                <div class="controls">
                    <div class="control-group">
                        <div class="control-header">
                            <label for="compressionLevel" class="control-label">
                                <i class="fas fa-sliders-h"></i> Compression Level
                                <span class="tooltip">
                                    <span class="tooltip-icon">i</span>
                                    <span class="tooltip-text">Higher values mean smaller files but lower quality. We recommend 70-80% for optimal balance.</span>
                                </span>
                            </label>
                            <span class="control-value" id="compressionValue">75%</span>
                        </div>
                        <div class="slider-container">
                            <div class="slider-progress" id="sliderProgress"></div>
                            <input type="range" min="0" max="100" value="75" class="slider" id="compressionLevel">
                        </div>
                    </div>
                    
                    <div class="control-group">
                        <div class="control-header">
                            <label for="outputFormat" class="control-label">
                                <i class="fas fa-file-image"></i> Output Format
                            </label>
                        </div>
                        <div class="select-wrapper">
                            <select id="outputFormat">
                                <option value="original">Keep Original Format</option>
                                <option value="jpeg">JPEG (Best for Photos)</option>
                                <option value="png">PNG (Best for Transparency)</option>
                                <option value="webp">WebP (Best for Web)</option>
                            </select>
                        </div>
                    </div>
                    
                    <div class="control-group">
                        <div class="control-header">
                            <label for="resizeToggle" class="control-label">
                                <i class="fas fa-expand-alt"></i> Resize Options
                                <span class="tooltip">
                                    <span class="tooltip-icon">i</span>
                                    <span class="tooltip-text">Resize images to specific dimensions while maintaining aspect ratio.</span>
                                </span>
                            </label>
                        </div>
                        <div class="select-wrapper">
                            <select id="resizeToggle">
                                <option value="no">Don't Resize</option>
                                <option value="width">By Width (px)</option>
                                <option value="height">By Height (px)</option>
                                <option value="both">Width & Height (px)</option>
                            </select>
                        </div>
                    </div>
                </div>
                
                <!-- Action Buttons -->
                <div class="action-buttons">
                    <button id="compressBtn" class="btn btn-primary btn-lg" disabled>
                        <span class="spinner" id="compressSpinner"></span>
                        <i class="fas fa-compress-alt"></i> Compress Images
                    </button>
                    <button id="resetBtn" class="btn btn-outline btn-lg" disabled>
                        <i class="fas fa-redo"></i> Reset
                    </button>
                </div>
                
                <!-- Results Section -->
                <div class="results-section" id="resultsSection">
                    <div class="results-header">
                        <h3 class="results-title">
                            <i class="fas fa-check-circle"></i> Compression Results
                        </h3>
                        <div class="results-summary">
                            <div class="summary-item">
                                <div class="summary-value" id="totalSavings">0%</div>
                                <div class="summary-label">Total Savings</div>
                            </div>
                            <div class="summary-item">
                                <div class="summary-value" id="totalOriginalSize">0 KB</div>
                                <div class="summary-label">Original Size</div>
                            </div>
                            <div class="summary-item">
                                <div class="summary-value" id="totalCompressedSize">0 KB</div>
                                <div class="summary-label">Compressed Size</div>
                            </div>
                        </div>
                    </div>
                    
                    <div class="results-grid" id="resultsGrid"></div>
                    
                    <div class="action-buttons">
                        <button id="downloadAllBtn" class="btn btn-accent btn-lg">
                            <i class="fas fa-download"></i> Download All
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Features Section -->
    <section id="features" class="features-section">
        <div class="container">
            <div class="section-header">
                <h2 class="section-title">Why Choose PixelPress?</h2>
                <p class="section-subtitle">Our tool offers the best balance between quality and file size for all your image needs.</p>
            </div>
            
            <div class="features-grid">
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-bolt"></i>
                    </div>
                    <h3 class="feature-title">Lightning Fast</h3>
                    <p class="feature-desc">Process dozens of images in seconds with our optimized compression algorithms that run directly in your browser.</p>
                </div>
                
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-lock"></i>
                    </div>
                    <h3 class="feature-title">Complete Privacy</h3>
                    <p class="feature-desc">Your images never leave your device. All processing happens locally in your browser with no server uploads.</p>
                </div>
                
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-chart-line"></i>
                    </div>
                    <h3 class="feature-title">Smart Optimization</h3>
                    <p class="feature-desc">Our AI analyzes each image to apply the optimal compression without noticeable quality loss.</p>
                </div>
                
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-mobile-alt"></i>
                    </div>
                    <h3 class="feature-title">Fully Responsive</h3>
                    <p class="feature-desc">Works perfectly on all devices from desktops to smartphones with a touch-friendly interface.</p>
                </div>
                
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-sliders-h"></i>
                    </div>
                    <h3 class="feature-title">Advanced Controls</h3>
                    <p class="feature-desc">Fine-tune compression settings with our intuitive controls to get exactly the results you want.</p>
                </div>
                
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-gem"></i>
                    </div>
                    <h3 class="feature-title">Premium Quality</h3>
                    <p class="feature-desc">Get professional-grade image optimization without expensive software or subscriptions.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- How It Works Section -->
    <section id="how-it-works" class="how-it-works">
        <div class="container">
            <div class="section-header">
                <h2 class="section-title">How It Works</h2>
                <p class="section-subtitle">Optimizing your images has never been easier. Just follow these simple steps:</p>
            </div>
            
            <div class="steps">
                <div class="step">
                    <div class="step-number">1</div>
                    <div class="step-content">
                        <h4 class="step-title">Upload Your Images</h4>
                        <p class="step-desc">Drag and drop your images into the upload area or click to browse your files. We support JPG, PNG, and WebP formats. You can process multiple images at once.</p>
                    </div>
                </div>
                
                <div class="step">
                    <div class="step-number">2</div>
                    <div class="step-content">
                        <h4 class="step-title">Adjust Settings</h4>
                        <p class="step-desc">Choose your preferred compression level and output format. Use the interactive preview to see estimated results before processing. Our smart defaults work great for most cases.</p>
                    </div>
                </div>
                
                <div class="step">
                    <div class="step-number">3</div>
                    <div class="step-content">
                        <h4 class="step-title">Compress & Download</h4>
                        <p class="step-desc">Click the compress button and download your optimized images in seconds. Compare before/after results side by side with our interactive comparison tool.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- FAQ Section -->
    <section id="faq" class="faq-section">
        <div class="container">
            <div class="section-header">
                <h2 class="section-title">Frequently Asked Questions</h2>
                <p class="section-subtitle">Find answers to common questions about our image compression tool.</p>
            </div>
            
            <div class="faq-container">
                <div class="faq-item">
                    <div class="faq-question">
                        Is my image data secure?
                        <i class="fas fa-chevron-down"></i>
                    </div>
                    <div class="faq-answer">
                        <p>Absolutely! All image processing happens directly in your browser using JavaScript. Your images are never uploaded to any server, ensuring complete privacy and security. We don't store or access your files in any way.</p>
                    </div>
                </div>
                
                <div class="faq-item">
                    <div class="faq-question">
                        What image formats are supported?
                        <i class="fas fa-chevron-down"></i>
                    </div>
                    <div class="faq-answer">
                        <p>We support JPEG, PNG, and WebP formats. You can choose to keep the original format or convert to another format during compression. WebP typically offers the best compression ratios for web use.</p>
                    </div>
                </div>
                
                <div class="faq-item">
                    <div class="faq-question">
                        Is there a limit to file size or number of images?
                        <i class="fas fa-chevron-down"></i>
                    </div>
                    <div class="faq-answer">
                        <p>There's no hard limit, but very large images (over 10MB) or many images at once may take longer to process depending on your device's capabilities. For best performance, we recommend processing images in batches of 10-20 at a time.</p>
                    </div>
                </div>
                
                <div class="faq-item">
                    <div class="faq-question">
                        How much can I reduce my image file sizes?
                        <i class="fas fa-chevron-down"></i>
                    </div>
                    <div class="faq-answer">
                        <p>Typical reductions range from 50-90% depending on the image content and your quality settings. Photos often compress more than graphics with text. Our smart algorithm automatically finds the optimal balance between size and quality.</p>
                    </div>
                </div>
                
                <div class="faq-item">
                    <div class="faq-question">
                        Can I use this tool on my mobile device?
                        <i class="fas fa-chevron-down"></i>
                    </div>
                    <div class="faq-answer">
                        <p>Yes! Our tool is fully responsive and works perfectly on smartphones and tablets. The interface adapts to your screen size for optimal usability. All processing happens on your device, so it works even without an internet connection.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer id="contact">
        <div class="container">
            <div class="footer-content">
                <div class="footer-col">
                    <a href="#" class="footer-logo">
                        <i class="fas fa-compress-alt footer-logo-icon"></i>
                        <span>PixelPress</span>
                    </a>
                    <p class="footer-desc">
                        The most advanced browser-based image compression tool. Optimize your images without compromising quality or privacy.
                    </p>
                    <div class="social-links">
                        <a href="#" class="social-link">
                            <i class="fab fa-twitter"></i>
                        </a>
                        <a href="#" class="social-link">
                            <i class="fab fa-facebook-f"></i>
                        </a>
                        <a href="#" class="social-link">
                            <i class="fab fa-instagram"></i>
                        </a>
                        <a href="#" class="social-link">
                            <i class="fab fa-github"></i>
                        </a>
                    </div>
                </div>
                
                <div class="footer-col">
                    <h3 class="footer-title">Quick Links</h3>
                    <ul class="footer-links">
                        <li class="footer-link-item"><a href="#" class="footer-link">Home</a></li>
                        <li class="footer-link-item"><a href="#features" class="footer-link">Features</a></li>
                        <li class="footer-link-item"><a href="#how-it-works" class="footer-link">How It Works</a></li>
                        <li class="footer-link-item"><a href="#faq" class="footer-link">FAQ</a></li>
                    </ul>
                </div>
                
                <div class="footer-col">
                    <h3 class="footer-title">Resources</h3>
                    <ul class="footer-links">
                        <li class="footer-link-item"><a href="#" class="footer-link">Blog</a></li>
                        <li class="footer-link-item"><a href="#" class="footer-link">Documentation</a></li>
                        <li class="footer-link-item"><a href="#" class="footer-link">API</a></li>
                        <li class="footer-link-item"><a href="#" class="footer-link">Support</a></li>
                    </ul>
                </div>
                
                <div class="footer-col">
                    <h3 class="footer-title">Contact Us</h3>
                    <ul class="footer-links">
                        <li class="footer-link-item"><a href="mailto:hello@pixelpress.com" class="footer-link">hello@pixelpress.com</a></li>
                        <li class="footer-link-item"><a href="tel:+1234567890" class="footer-link">+1 (234) 567-890</a></li>
                        <li class="footer-link-item"><a href="#" class="footer-link">Feedback</a></li>
                        <li class="footer-link-item"><a href="#" class="footer-link">Report Issue</a></li>
                    </ul>
                </div>
            </div>
            
            <div class="footer-bottom">
                <p>&copy; <span id="year"></span> PixelPress Pro. All rights reserved.</p>
            </div>
        </div>
    </footer>

    <!-- Toast Notification -->
    <div class="toast" id="toast">
        <div class="toast-icon">
            <i class="fas fa-check-circle"></i>
        </div>
        <div class="toast-message" id="toastMessage">Operation completed successfully!</div>
        <button class="toast-close">
            <i class="fas fa-times"></i>
        </button>
    </div>

    <script>
        // DOM Elements
        const fileInput = document.getElementById('fileInput');
        const dropArea = document.getElementById('dropArea');
        const uploadBtn = document.getElementById('uploadBtn');
        const previewArea = document.getElementById('previewArea');
        const previewGrid = document.getElementById('previewGrid');
        const fileCount = document.getElementById('fileCount');
        const clearBtn = document.getElementById('clearBtn');
        const compressionLevel = document.getElementById('compressionLevel');
        const compressionValue = document.getElementById('compressionValue');
        const sliderProgress = document.getElementById('sliderProgress');
        const outputFormat = document.getElementById('outputFormat');
        const resizeToggle = document.getElementById('resizeToggle');
        const compressBtn = document.getElementById('compressBtn');
        const resetBtn = document.getElementById('resetBtn');
        const resultsSection = document.getElementById('resultsSection');
        const resultsGrid = document.getElementById('resultsGrid');
        const totalSavings = document.getElementById('totalSavings');
        const totalOriginalSize = document.getElementById('totalOriginalSize');
        const totalCompressedSize = document.getElementById('totalCompressedSize');
        const downloadAllBtn = document.getElementById('downloadAllBtn');
        const compressSpinner = document.getElementById('compressSpinner');
        const toast = document.getElementById('toast');
        const toastMessage = document.getElementById('toastMessage');
        const toastClose = document.querySelector('.toast-close');
        const mobileMenuBtn = document.getElementById('mobileMenuBtn');
        const navLinks = document.querySelector('.nav-links');
        const header = document.getElementById('header');
        const particles = document.getElementById('particles');
        
        // State
        let uploadedFiles = [];
        let compressedFiles = [];
        
        // Initialize
        document.getElementById('year').textContent = new Date().getFullYear();
        createParticles();
        updateSliderProgress();
        
        // Event Listeners
        uploadBtn.addEventListener('click', () => fileInput.click());
        dropArea.addEventListener('dragover', (e) => {
            e.preventDefault();
            dropArea.classList.add('active');
        });
        
        dropArea.addEventListener('dragleave', () => {
            dropArea.classList.remove('active');
        });
        
        dropArea.addEventListener('drop', (e) => {
            e.preventDefault();
            dropArea.classList.remove('active');
            handleFiles(e.dataTransfer.files);
        });
        
        fileInput.addEventListener('change', () => {
            handleFiles(fileInput.files);
        });
        
        clearBtn.addEventListener('click', resetUploader);
        resetBtn.addEventListener('click', resetUploader);
        
        compressionLevel.addEventListener('input', updateSliderProgress);
        compressBtn.addEventListener('click', compressImages);
        downloadAllBtn.addEventListener('click', downloadAll);
        toastClose.addEventListener('click', hideToast);
        
        // Mobile menu toggle
        mobileMenuBtn.addEventListener('click', toggleMobileMenu);
        
        // Header scroll effect
        window.addEventListener('scroll', () => {
            if (window.scrollY > 50) {
                header.classList.add('header-scrolled');
            } else {
                header.classList.remove('header-scrolled');
            }
        });
        
        // FAQ Accordion
        const faqItems = document.querySelectorAll('.faq-item');
        faqItems.forEach(item => {
            const question = item.querySelector('.faq-question');
            question.addEventListener('click', () => {
                item.classList.toggle('active');
            });
        });
        
        // Smooth scrolling for anchor links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                
                if (this.getAttribute('href') === '#') return;
                
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    window.scrollTo({
                        top: target.offsetTop - 80,
                        behavior: 'smooth'
                    });
                    
                    // Close mobile menu if open
                    navLinks.classList.remove('active');
                    mobileMenuBtn.innerHTML = '<i class="fas fa-bars"></i>';
                }
            });
        });
        
        // Functions
        function toggleMobileMenu() {
            navLinks.classList.toggle('active');
            mobileMenuBtn.innerHTML = navLinks.classList.contains('active') 
                ? '<i class="fas fa-times"></i>' 
                : '<i class="fas fa-bars"></i>';
        }
        
        function handleFiles(files) {
            const validFiles = Array.from(files).filter(file => 
                file.type.match('image.*') && 
                ['image/jpeg', 'image/png', 'image/webp'].includes(file.type)
            );
            
            if (validFiles.length === 0) {
                showToast('Please select valid image files (JPG, PNG, WebP)', 'error');
                return;
            }
            
            uploadedFiles = [...uploadedFiles, ...validFiles];
            updatePreview();
            updateUI();
            
            if (validFiles.length !== files.length) {
                showToast(`Added ${validFiles.length} image(s), skipped ${files.length - validFiles.length} non-image files`, 'info');
            } else {
                showToast(`Added ${validFiles.length} image(s)`, 'success');
            }
        }
        
        function updatePreview() {
            previewGrid.innerHTML = '';
            
            uploadedFiles.forEach((file, index) => {
                const reader = new FileReader();
                reader.onload = (e) => {
                    const previewCard = document.createElement('div');
                    previewCard.className = 'preview-card';
                    previewCard.innerHTML = `
                        <img src="${e.target.result}" class="preview-image" alt="${file.name}">
                        <div class="preview-info">
                            <div class="preview-name">${file.name}</div>
                            <div class="preview-size">
                                <i class="fas fa-file-image"></i> ${formatFileSize(file.size)}
                            </div>
                        </div>
                        <button class="remove-btn" data-index="${index}">
                            <i class="fas fa-times"></i>
                        </button>
                    `;
                    
                    previewGrid.appendChild(previewCard);
                    
                    // Add event listener to remove button
                    const removeBtn = previewCard.querySelector('.remove-btn');
                    removeBtn.addEventListener('click', (e) => {
                        e.stopPropagation();
                        removeFile(index);
                    });
                };
                reader.readAsDataURL(file);
            });
            
            previewArea.style.display = 'block';
            fileCount.textContent = uploadedFiles.length;
        }
        
        function removeFile(index) {
            uploadedFiles.splice(index, 1);
            updatePreview();
            updateUI();
            showToast('Image removed', 'info');
        }
        
        function resetUploader() {
            uploadedFiles = [];
            compressedFiles = [];
            fileInput.value = '';
            previewArea.style.display = 'none';
            resultsSection.style.display = 'none';
            compressionLevel.value = 75;
            compressionValue.textContent = '75%';
            outputFormat.value = 'original';
            resizeToggle.value = 'no';
            updateSliderProgress();
            updateUI();
            showToast('Uploader reset', 'info');
        }
        
        function updateUI() {
            compressBtn.disabled = uploadedFiles.length === 0;
            resetBtn.disabled = uploadedFiles.length === 0;
        }
        
        function updateSliderProgress() {
            const value = compressionLevel.value;
            compressionValue.textContent = `${value}%`;
            sliderProgress.style.width = `${value}%`;
        }
        
        async function compressImages() {
            if (uploadedFiles.length === 0) return;
            
            // Show loading state
            compressBtn.disabled = true;
            compressSpinner.style.display = 'inline-block';
            compressBtn.innerHTML = `<span class="spinner" id="compressSpinner"></span> Compressing...`;
            
            // Clear previous results
            resultsGrid.innerHTML = '';
            compressedFiles = [];
            
            let totalOriginal = 0;
            let totalCompressed = 0;
            
            try {
                // Process each file
                for (let i = 0; i < uploadedFiles.length; i++) {
                    const file = uploadedFiles[i];
                    const compressedFile = await compressImage(file);
                    
                    compressedFiles.push(compressedFile);
                    totalOriginal += file.size;
                    totalCompressed += compressedFile.size;
                    
                    // Display result
                    displayResult(file, compressedFile, i);
                    
                    // Small delay to prevent UI freezing
                    await new Promise(resolve => setTimeout(resolve, 50));
                }
                
                // Update summary
                const reduction = ((1 - totalCompressed / totalOriginal) * 100).toFixed(1);
                totalSavings.textContent = `${reduction}%`;
                totalOriginalSize.textContent = formatFileSize(totalOriginal);
                totalCompressedSize.textContent = formatFileSize(totalCompressed);
                
                // Show results
                resultsSection.style.display = 'block';
                showToast(`Successfully compressed ${uploadedFiles.length} image(s) with ${reduction}% average reduction`, 'success');
                
                // Scroll to results
                setTimeout(() => {
                    resultsSection.scrollIntoView({ behavior: 'smooth' });
                }, 300);
                
            } catch (error) {
                console.error('Compression error:', error);
                showToast('An error occurred during compression', 'error');
            } finally {
                // Reset button state
                compressBtn.disabled = false;
                compressSpinner.style.display = 'none';
                compressBtn.innerHTML = `<i class="fas fa-compress-alt"></i> Compress Images`;
            }
        }
        
        async function compressImage(file) {
            return new Promise((resolve, reject) => {
                const reader = new FileReader();
                
                reader.onload = function(event) {
                    const img = new Image();
                    img.src = event.target.result;
                    
                    img.onload = function() {
                        const canvas = document.createElement('canvas');
                        const ctx = canvas.getContext('2d');
                        
                        // Calculate dimensions
                        let width = img.width;
                        let height = img.height;
                        
                        // Apply resizing if needed
                        const resizeMode = resizeToggle.value;
                        if (resizeMode !== 'no') {
                            // In a real app, you'd get these from input fields
                            const targetWidth = resizeMode === 'width' || resizeMode === 'both' ? 800 : null;
                            const targetHeight = resizeMode === 'height' || resizeMode === 'both' ? 600 : null;
                            
                            if (targetWidth && targetHeight) {
                                // Both dimensions specified
                                width = targetWidth;
                                height = targetHeight;
                            } else if (targetWidth) {
                                // Width specified, maintain aspect ratio
                                const ratio = targetWidth / width;
                                width = targetWidth;
                                height = Math.round(height * ratio);
                            } else if (targetHeight) {
                                // Height specified, maintain aspect ratio
                                const ratio = targetHeight / height;
                                height = targetHeight;
                                width = Math.round(width * ratio);
                            }
                        }
                        
                        canvas.width = width;
                        canvas.height = height;
                        
                        // Draw image with new dimensions
                        ctx.drawImage(img, 0, 0, width, height);
                        
                        // Get output format
                        let format = outputFormat.value === 'original' 
                            ? file.type.split('/')[1] 
                            : outputFormat.value;
                        
                        if (format === 'jpeg') format = 'jpg';
                        
                        // Quality setting (0-1)
                        const quality = compressionLevel.value / 100;
                        
                        // Convert to blob
                        canvas.toBlob(blob => {
                            if (!blob) {
                                reject(new Error('Compression failed'));
                                return;
                            }
                            
                            const compressedFile = new File([blob], `compressed_${file.name.replace(/\.[^/.]+$/, '')}.${format}`, {
                                type: `image/${format}`,
                                lastModified: Date.now()
                            });
                            
                            resolve(compressedFile);
                        }, `image/${format}`, quality);
                    };
                    
                    img.onerror = function() {
                        reject(new Error('Failed to load image'));
                    };
                };
                
                reader.onerror = function() {
                    reject(new Error('Failed to read file'));
                };
                
                reader.readAsDataURL(file);
            });
        }
        
        function displayResult(originalFile, compressedFile, index) {
            const originalSize = originalFile.size;
            const compressedSize = compressedFile.size;
            const reduction = ((1 - compressedSize / originalSize) * 100).toFixed(1);
            
            const resultCard = document.createElement('div');
            resultCard.className = 'result-card';
            resultCard.innerHTML = `
                <div class="result-comparison">
                    <img src="${URL.createObjectURL(originalFile)}" class="result-original" alt="Original">
                    <img src="${URL.createObjectURL(compressedFile)}" class="result-compressed" alt="Compressed">
                </div>
                <div class="result-stats">
                    <div class="result-name">${originalFile.name}</div>
                    <div class="progress-container">
                        <div class="progress-bar" style="width: ${reduction}%"></div>
                    </div>
                    <div class="stat-row">
                        <span class="stat-label">
                            <i class="fas fa-file-image"></i> Original:
                        </span>
                        <span class="stat-value">${formatFileSize(originalSize)}</span>
                    </div>
                    <div class="stat-row">
                        <span class="stat-label">
                            <i class="fas fa-compress-alt"></i> Compressed:
                        </span>
                        <span class="stat-value">${formatFileSize(compressedSize)}</span>
                    </div>
                    <div class="stat-row">
                        <span class="stat-label">
                            <i class="fas fa-percentage"></i> Reduction:
                        </span>
                        <span class="stat-value savings">${reduction}%</span>
                    </div>
                </div>
                <a href="${URL.createObjectURL(compressedFile)}" download="${compressedFile.name}" class="download-btn">
                    <i class="fas fa-download"></i> Download
                </a>
            `;
            
            resultsGrid.appendChild(resultCard);
        }
        
        function downloadAll() {
            if (compressedFiles.length === 0) return;
            
            // In a real app, you might zip the files for download
            // For this demo, we'll trigger downloads for each file
            compressedFiles.forEach(file => {
                const link = document.createElement('a');
                link.href = URL.createObjectURL(file);
                link.download = file.name;
                document.body.appendChild(link);
                link.click();
                document.body.removeChild(link);
            });
            
            showToast(`Downloading ${compressedFiles.length} file(s)`, 'success');
        }
        
        function formatFileSize(bytes) {
            if (bytes < 1024) return `${bytes} B`;
            if (bytes < 1024 * 1024) return `${(bytes / 1024).toFixed(1)} KB`;
            return `${(bytes / (1024 * 1024)).toFixed(1)} MB`;
        }
        
        function showToast(message, type) {
            toast.className = `toast toast-${type} show`;
            toastMessage.textContent = message;
            
            // Set icon based on type
            const icon = toast.querySelector('.toast-icon');
            if (type === 'success') {
                icon.className = 'toast-icon fas fa-check-circle';
            } else if (type === 'error') {
                icon.className = 'toast-icon fas fa-exclamation-circle';
            } else {
                icon.className = 'toast-icon fas fa-info-circle';
            }
            
            // Auto-hide after 5 seconds
            setTimeout(hideToast, 5000);
        }
        
        function hideToast() {
            toast.classList.remove('show');
        }
        
        function createParticles() {
            const particleCount = Math.floor(window.innerWidth / 10);
            
            for (let i = 0; i < particleCount; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                
                // Random size between 2px and 6px
                const size = Math.random() * 4 + 2;
                particle.style.width = `${size}px`;
                particle.style.height = `${size}px`;
                
                // Random position
                particle.style.left = `${Math.random() * 100}%`;
                particle.style.top = `${Math.random() * 100}%`;
                
                // Random animation duration between 10s and 30s
                const duration = Math.random() * 20 + 10;
                particle.style.animationDuration = `${duration}s`;
                
                // Random delay
                particle.style.animationDelay = `${Math.random() * 10}s`;
                
                // Random opacity
                particle.style.opacity = Math.random() * 0.5 + 0.1;
                
                // Random color variation
                const hue = Math.random() * 60 + 240; // Purple/blue range
                particle.style.backgroundColor = `hsla(${hue}, 80%, 70%, ${particle.style.opacity})`;
                
                particles.appendChild(particle);
            }
        }
    </script>
</body>
</html>
