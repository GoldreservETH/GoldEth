# GoldEth
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Gold Reserve Token | Secure Gold-Backed Cryptocurrency</title>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700;900&family=Montserrat:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <script src="https://cdn.jsdelivr.net/npm/web3@1.5.3/dist/web3.min.js"></script>
    <style>
        :root {
            --primary-500: #f5be14;
            --primary-600: #c49810;
            --secondary-700: #1f2937;
            --secondary-800: #111827;
            --secondary-900: #0a0e17;
            --success: #22c55e;
            --error: #ef4444;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            background: linear-gradient(135deg, #0a0e17 0%, #1f2937 100%);
            color: #f3f4f6;
            font-family: 'Montserrat', sans-serif;
            line-height: 1.6;
            scroll-behavior: smooth;
        }
        
        /* Header & Navigation */
        header {
            background-color: rgba(31, 41, 55, 0.9);
            backdrop-filter: blur(10px);
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }
        
        nav {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            align-items: center;
            padding: 15px 0;
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 12px;
        }
        
        .logo-icon {
            background-color: var(--primary-500);
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .logo-icon i {
            color: var(--secondary-900);
            font-size: 20px;
        }
        
        .logo-text h1 {
            font-family: 'Playfair Display', serif;
            font-size: 22px;
            font-weight: 700;
        }
        
        .logo-text p {
            font-size: 12px;
            color: var(--primary-500);
        }
        
        .nav-links {
            display: flex;
            gap: 20px;
            margin: 10px 0;
        }
        
        .nav-links a {
            color: #f3f4f6;
            text-decoration: none;
            font-weight: 500;
            padding: 8px 15px;
            border-radius: 6px;
            transition: all 0.3s ease;
        }
        
        .nav-links a:hover {
            background-color: rgba(245, 190, 20, 0.1);
            color: var(--primary-500);
        }
        
        .wallet-btn {
            background: linear-gradient(135deg, var(--primary-500) 0%, var(--primary-600) 100%);
            color: #111827;
            border: none;
            border-radius: 30px;
            padding: 10px 25px;
            font-weight: 600;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 8px;
            transition: all 0.3s ease;
        }
        
        .wallet-btn:hover {
            opacity: 0.9;
            transform: translateY(-2px);
        }
        
        .wallet-btn.connected {
            background: linear-gradient(135deg, var(--success) 0%, #16a34a 100%);
        }
        
        /* Hero Section */
        .hero {
            padding: 80px 0;
            position: relative;
            overflow: hidden;
        }
        
        .hero-bg {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(to bottom, rgba(10, 14, 23, 0.9), rgba(10, 14, 23, 0.95));
            z-index: -2;
        }
        
        .hero-pattern {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: url("data:image/svg+xml,%3Csvg width='100' height='100' viewBox='0 0 100 100' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M11 18c3.866 0 7-3.134 7-7s-3.134-7-7-7-7 3.134-7 7 3.134 7 7 7zm48 25c3.866 0 7-3.134 7-7s-3.134-7-7-7-7 3.134-7 7 3.134 7 7 7zm-43-7c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zm63 31c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zM34 90c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zm56-76c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zM12 86c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm28-65c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm23-11c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zm-6 60c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm29 22c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zM32 63c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zm57-13c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zm-9-21c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2zM60 91c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2zM35 41c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2zM12 60c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2z' fill='%23f5be14' fill-opacity='0.05' fill-rule='evenodd'/%3E%3C/svg%3E");
            opacity: 0.1;
            z-index: -1;
        }
        
        .hero-content {
            text-align: center;
            max-width: 800px;
            margin: 0 auto;
        }
        
        .presale-badge {
            display: inline-block;
            background-color: rgba(31, 41, 55, 0.7);
            color: var(--primary-500);
            padding: 10px 25px;
            border-radius: 30px;
            margin-bottom: 25px;
            font-weight: 600;
            animation: pulse 2s infinite;
        }
        
        @keyframes pulse {
            0% { box-shadow: 0 0 0 0 rgba(245, 190, 20, 0.4); }
            70% { box-shadow: 0 0 0 15px rgba(245, 190, 20, 0); }
            100% { box-shadow: 0 0 0 0 rgba(245, 190, 20, 0); }
        }
        
        .hero h1 {
            font-family: 'Playfair Display', serif;
            font-size: 3.5rem;
            font-weight: 700;
            margin-bottom: 20px;
            line-height: 1.2;
        }
        
        .gold-text {
            background: linear-gradient(135deg, var(--primary-500) 0%, var(--primary-600) 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }
        
        .hero p {
            font-size: 1.25rem;
            opacity: 0.9;
            margin-bottom: 40px;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
        }
        
        .cta-buttons {
            display: flex;
            justify-content: center;
            gap: 20px;
            flex-wrap: wrap;
            margin-bottom: 50px;
        }
        
        .btn-primary {
            background: linear-gradient(135deg, var(--primary-500) 0%, var(--primary-600) 100%);
            color: #111827;
            border: none;
            border-radius: 50px;
            padding: 15px 35px;
            font-size: 1.1rem;
            font-weight: 600;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 10px;
            transition: all 0.3s ease;
        }
        
        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(245, 190, 20, 0.3);
        }
        
        .btn-secondary {
            background: transparent;
            color: var(--primary-500);
            border: 2px solid var(--primary-500);
            border-radius: 50px;
            padding: 15px 35px;
            font-size: 1.1rem;
            font-weight: 600;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 10px;
            transition: all 0.3s ease;
        }
        
        .btn-secondary:hover {
            background-color: rgba(245, 190, 20, 0.1);
            transform: translateY(-3px);
        }
        
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
            gap: 20px;
            max-width: 800px;
            margin: 0 auto;
        }
        
        .stat-card {
            background-color: rgba(31, 41, 55, 0.6);
            border: 1px solid rgba(55, 65, 81, 0.5);
            border-radius: 10px;
            padding: 20px;
            text-align: center;
        }
        
        .stat-value {
            font-size: 2rem;
            font-weight: 700;
            color: var(--primary-500);
            margin-bottom: 5px;
        }
        
        .stat-label {
            font-size: 0.9rem;
            opacity: 0.8;
        }
        
        /* Sections */
        section {
            padding: 80px 0;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 60px;
        }
        
        .section-title h2 {
            font-family: 'Playfair Display', serif;
            font-size: 2.5rem;
            font-weight: 700;
            margin-bottom: 15px;
        }
        
        .section-title p {
            font-size: 1.1rem;
            opacity: 0.8;
            max-width: 600px;
            margin: 0 auto;
        }
        
        /* Investment Cards */
        .cards-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }
        
        .card {
            background-color: var(--secondary-800);
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            transition: all 0.4s ease;
            position: relative;
        }
        
        .card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 40px rgba(245, 190, 20, 0.2);
        }
        
        .card-header {
            padding: 30px 20px 20px;
            text-align: center;
            position: relative;
        }
        
        .card-badge {
            position: absolute;
            top: -10px;
            right: 20px;
            background: linear-gradient(135deg, #4ade80, #22c55e);
            color: #111827;
            font-weight: 700;
            padding: 5px 15px;
            border-radius: 20px;
            transform: rotate(5deg);
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
            font-size: 0.8rem;
        }
        
        .card-icon {
            width: 70px;
            height: 70px;
            background-color: rgba(31, 41, 55, 0.7);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 20px;
        }
        
        .card-icon i {
            font-size: 30px;
            color: var(--primary-500);
        }
        
        .card-title {
            font-size: 1.5rem;
            font-weight: 600;
            margin-bottom: 10px;
        }
        
        .card-price {
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--primary-500);
            margin-bottom: 5px;
        }
        
        .card-subtitle {
            font-size: 1rem;
            opacity: 0.8;
        }
        
        .card-body {
            padding: 20px;
        }
        
        .card-features {
            list-style: none;
            margin-bottom: 30px;
        }
        
        .card-features li {
            padding: 10px 0;
            display: flex;
            align-items: center;
            gap: 10px;
            border-bottom: 1px solid rgba(55, 65, 81, 0.5);
        }
        
        .card-features li:last-child {
            border-bottom: none;
        }
        
        .card-features li i {
            color: var(--primary-500);
        }
        
        .card-button {
            display: block;
            width: 100%;
            padding: 15px;
            text-align: center;
            background-color: rgba(31, 41, 55, 0.7);
            color: #f3f4f6;
            border: none;
            border-radius: 8px;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .card-button:hover {
            background-color: var(--primary-500);
            color: #111827;
        }
        
        /* Token Purchase Section */
        .presale-section {
            background-color: var(--secondary-700);
        }
        
        .presale-container {
            background-color: var(--secondary-800);
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.3);
            max-width: 1000px;
            margin: 0 auto;
        }
        
        .presale-header {
            padding: 30px;
            text-align: center;
            background-color: rgba(31, 41, 55, 0.7);
            border-bottom: 1px solid rgba(55, 65, 81, 0.5);
        }
        
        .presale-header h3 {
            font-size: 1.5rem;
            margin-bottom: 15px;
        }
        
        .countdown {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-top: 20px;
        }
        
        .countdown-box {
            background-color: rgba(31, 41, 55, 0.6);
            border: 1px solid var(--primary-500);
            border-radius: 10px;
            padding: 15px;
            min-width: 80px;
            text-align: center;
        }
        
        .countdown-value {
            font-size: 2rem;
            font-weight: 700;
            color: var(--primary-500);
            line-height: 1;
        }
        
        .countdown-label {
            font-size: 0.8rem;
            text-transform: uppercase;
            opacity: 0.8;
            margin-top: 5px;
        }
        
        .presale-content {
            display: grid;
            grid-template-columns: 1fr;
            gap: 30px;
            padding: 30px;
        }
        
        @media (min-width: 992px) {
            .presale-content {
                grid-template-columns: 1fr 1fr;
            }
        }
        
        .presale-info {
            background-color: rgba(31, 41, 55, 0.6);
            border-radius: 15px;
            padding: 25px;
        }
        
        .presale-info h4 {
            font-size: 1.3rem;
            margin-bottom: 20px;
            color: var(--primary-500);
        }
        
        .info-item {
            display: flex;
            justify-content: space-between;
            padding: 12px 0;
            border-bottom: 1px solid rgba(55, 65, 81, 0.5);
        }
        
        .info-item:last-child {
            border-bottom: none;
        }
        
        .progress-container {
            margin: 20px 0;
        }
        
        .progress-bar {
            height: 12px;
            background-color: rgba(31, 41, 55, 0.7);
            border-radius: 10px;
            overflow: hidden;
            margin-top: 10px;
        }
        
        .progress-fill {
            height: 100%;
            background: linear-gradient(to right, var(--primary-500), var(--primary-600));
            border-radius: 10px;
            width: 72%;
            transition: width 1s ease;
        }
        
        .bonus-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px;
            background-color: rgba(31, 41, 55, 0.7);
            border-radius: 10px;
            margin-bottom: 15px;
        }
        
        .bonus-item:last-child {
            margin-bottom: 0;
        }
        
        .bonus-highlight {
            font-weight: 700;
            color: var(--primary-500);
        }
        
        .purchase-box {
            background-color: rgba(31, 41, 55, 0.6);
            border-radius: 15px;
            padding: 25px;
        }
        
        .purchase-header {
            text-align: center;
            margin-bottom: 25px;
        }
        
        .purchase-badge {
            display: inline-block;
            background: linear-gradient(135deg, var(--primary-500), var(--primary-600));
            color: #111827;
            padding: 8px 20px;
            border-radius: 30px;
            font-weight: 600;
            margin-bottom: 15px;
        }
        
        .purchase-header h4 {
            font-size: 1.5rem;
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 500;
        }
        
        .input-group {
            position: relative;
        }
        
        .input-group input {
            width: 100%;
            padding: 15px 20px;
            background-color: rgba(31, 41, 55, 0.7);
            border: 1px solid rgba(55, 65, 81, 0.5);
            border-radius: 10px;
            color: #f3f4f6;
            font-size: 1.1rem;
        }
        
        .input-group input:focus {
            outline: none;
            border-color: var(--primary-500);
        }
        
        .input-icon {
            position: absolute;
            right: 15px;
            top: 50%;
            transform: translateY(-50%);
            color: var(--primary-500);
            font-size: 1.2rem;
        }
        
        .input-info {
            display: flex;
            justify-content: space-between;
            margin-top: 8px;
            font-size: 0.9rem;
            opacity: 0.8;
        }
        
        .summary-box {
            background-color: rgba(31, 41, 55, 0.7);
            border-radius: 10px;
            padding: 20px;
            margin: 25px 0;
        }
        
        .summary-item {
            display: flex;
            justify-content: space-between;
            margin-bottom: 10px;
        }
        
        .summary-item:last-child {
            margin-bottom: 0;
        }
        
        .btn-purchase {
            width: 100%;
            padding: 18px;
            background: linear-gradient(135deg, var(--primary-500), var(--primary-600));
            color: #111827;
            border: none;
            border-radius: 10px;
            font-size: 1.1rem;
            font-weight: 700;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            transition: all 0.3s ease;
        }
        
        .btn-purchase:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(245, 190, 20, 0.4);
        }
        
        .terms {
            text-align: center;
            margin-top: 15px;
            font-size: 0.9rem;
            opacity: 0.8;
        }
        
        .terms a {
            color: var(--primary-500);
            text-decoration: none;
        }
        
        /* Wallet Modal */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.7);
            z-index: 1000;
            justify-content: center;
            align-items: center;
        }
        
        .modal-content {
            background-color: var(--secondary-800);
            border-radius: 15px;
            width: 90%;
            max-width: 500px;
            overflow: hidden;
        }
        
        .modal-header {
            padding: 20px;
            background-color: rgba(31, 41, 55, 0.7);
            border-bottom: 1px solid rgba(55, 65, 81, 0.5);
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .modal-header h3 {
            font-size: 1.3rem;
        }
        
        .close-modal {
            background: none;
            border: none;
            color: #f3f4f6;
            font-size: 1.5rem;
            cursor: pointer;
        }
        
        .modal-body {
            padding: 30px;
        }
        
        .wallet-option {
            display: flex;
            align-items: center;
            padding: 20px;
            background-color: rgba(31, 41, 55, 0.6);
            border-radius: 10px;
            margin-bottom: 15px;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .wallet-option:hover {
            background-color: rgba(31, 41, 55, 0.8);
            transform: translateY(-2px);
        }
        
        .wallet-option:last-child {
            margin-bottom: 0;
        }
        
        .wallet-icon {
            width: 50px;
            height: 50px;
            background-color: rgba(31, 41, 55, 0.7);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-right: 20px;
        }
        
        .wallet-icon i {
            font-size: 24px;
            color: var(--primary-500);
        }
        
        .wallet-details h4 {
            font-size: 1.2rem;
            margin-bottom: 5px;
        }
        
        .wallet-details p {
            font-size: 0.9rem;
            opacity: 0.8;
        }
        
        /* Notification */
        .notification {
            position: fixed;
            bottom: 20px;
            right: 20px;
            padding: 15px 25px;
            border-radius: 10px;
            font-weight: 600;
            z-index: 1000;
            display: flex;
            align-items: center;
            gap: 10px;
            opacity: 0;
            transform: translateY(20px);
            transition: all 0.3s ease;
        }
        
        .notification.show {
            opacity: 1;
            transform: translateY(0);
        }
        
        .notification.success {
            background-color: rgba(34, 197, 94, 0.9);
            color: #111827;
        }
        
        .notification.error {
            background-color: rgba(239, 68, 68, 0.9);
            color: white;
        }
        
        /* Footer */
        footer {
            background-color: var(--secondary-900);
            padding: 60px 0 30px;
        }
        
        .footer-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
            margin-bottom: 40px;
        }
        
        .footer-col h4 {
            font-size: 1.3rem;
            margin-bottom: 20px;
            color: var(--primary-500);
        }
        
        .footer-about {
            display: flex;
            flex-direction: column;
        }
        
        .footer-logo {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 20px;
        }
        
        .footer-logo .logo-icon {
            width: 40px;
            height: 40px;
        }
        
        .footer-logo h3 {
            font-family: 'Playfair Display', serif;
            font-size: 1.5rem;
        }
        
        .footer-about p {
            margin-bottom: 20px;
            opacity: 0.8;
        }
        
        .social-links {
            display: flex;
            gap: 15px;
        }
        
        .social-link {
            width: 40px;
            height: 40px;
            background-color: rgba(31, 41, 55, 0.7);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s ease;
        }
        
        .social-link:hover {
            background-color: var(--primary-500);
            transform: translateY(-3px);
        }
        
        .social-link i {
            color: #f3f4f6;
        }
        
        .footer-links {
            list-style: none;
        }
        
        .footer-links li {
            margin-bottom: 12px;
        }
        
        .footer-links a {
            color: #f3f4f6;
            text-decoration: none;
            opacity: 0.8;
            transition: all 0.3s ease;
        }
        
        .footer-links a:hover {
            opacity: 1;
            color: var(--primary-500);
        }
        
        .contact-info {
            list-style: none;
        }
        
        .contact-info li {
            display: flex;
            align-items: flex-start;
            gap: 15px;
            margin-bottom: 20px;
        }
        
        .contact-info i {
            color: var(--primary-500);
            font-size: 1.2rem;
            margin-top: 3px;
        }
        
        .footer-bottom {
            text-align: center;
            padding-top: 30px;
            border-top: 1px solid rgba(55, 65, 81, 0.5);
        }
        
        .footer-bottom p {
            opacity: 0.7;
            font-size: 0.9rem;
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .cta-buttons {
                flex-direction: column;
                align-items: center;
            }
            
            .btn-primary, .btn-secondary {
                width: 100%;
                max-width: 300px;
            }
            
            .nav-links {
                width: 100%;
                justify-content: center;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container">
            <nav>
                <div class="logo">
                    <div class="logo-icon">
                        <i class="fas fa-coins"></i>
                    </div>
                    <div class="logo-text">
                        <h1>GOLD RESERVE TOKEN</h1>
                        <p>Secure Gold-Backed Cryptocurrency</p>
                    </div>
                </div>
                
                <div class="nav-links">
                    <a href="#presale">Presale</a>
                    <a href="#investment">Investment</a>
                    <a href="#benefits">Benefits</a>
                    <a href="#security">Security</a>
                    <a href="#faq">FAQ</a>
                </div>
                
                <button id="connectWallet" class="wallet-btn">
                    <i class="fas fa-wallet"></i>
                    <span id="walletText">Connect Wallet</span>
                </button>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-bg"></div>
        <div class="hero-pattern"></div>
        <div class="container">
            <div class="hero-content">
                <div class="presale-badge">
                    <i class="fas fa-bolt"></i> Presale Live - Limited Time Offer!
                </div>
                <h1><span class="gold-text">Gold-Backed</span> Crypto For Modern Investors</h1>
                <p>Secure, affordable, and accessible. Invest in physical gold with cryptocurrency convenience. Start with as little as $10.</p>
                
                <div class="cta-buttons">
                    <a href="#presale" class="btn-primary">
                        <i class="fas fa-gem"></i> Join Presale - From $10
                    </a>
                    <a href="#investment" class="btn-secondary">
                        <i class="fas fa-chart-line"></i> View Investment Plans
                    </a>
                </div>
                
                <div class="stats-grid">
                    <div class="stat-card">
                        <div class="stat-value">$5M+</div>
                        <div class="stat-label">Gold Reserves</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-value">24K</div>
                        <div class="stat-label">Pure Gold</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-value">98%</div>
                        <div class="stat-label">Lower Fees</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-value">3</div>
                        <div class="stat-label">Secure Vaults</div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Investment Options -->
    <section id="investment">
        <div class="container">
            <div class="section-title">
                <h2>Affordable Investment Options</h2>
                <p>Start with just $10 and grow your gold portfolio</p>
            </div>
            
            <div class="cards-container">
                <!-- Starter Tier -->
                <div class="card">
                    <div class="card-header">
                        <div class="card-badge">Best Value</div>
                        <div class="card-icon">
                            <i class="fas fa-gem"></i>
                        </div>
                        <h3 class="card-title">Starter</h3>
                        <div class="card-price">$10-49</div>
                        <p class="card-subtitle">Perfect for first-time investors</p>
                    </div>
                    <div class="card-body">
                        <ul class="card-features">
                            <li><i class="fas fa-check-circle"></i> 5-24 GRT Tokens</li>
                            <li><i class="fas fa-check-circle"></i> Basic Investor Status</li>
                            <li><i class="fas fa-check-circle"></i> Email Updates</li>
                            <li><i class="fas fa-check-circle"></i> Community Access</li>
                            <li><i class="fas fa-check-circle"></i> +5% Bonus Tokens</li>
                        </ul>
                        <button class="card-button">Start Investing</button>
                    </div>
                </div>
                
                <!-- Silver Tier -->
                <div class="card">
                    <div class="card-header">
                        <div class="card-badge">Most Popular</div>
                        <div class="card-icon">
                            <i class="fas fa-crown"></i>
                        </div>
                        <h3 class="card-title">Silver Tier</h3>
                        <div class="card-price">$50-199</div>
                        <p class="card-subtitle">Great for building your gold portfolio</p>
                    </div>
                    <div class="card-body">
                        <ul class="card-features">
                            <li><i class="fas fa-check-circle"></i> 25-99 GRT Tokens</li>
                            <li><i class="fas fa-check-circle"></i> Priority Support</li>
                            <li><i class="fas fa-check-circle"></i> Early Access to Features</li>
                            <li><i class="fas fa-check-circle"></i> Silver NFT Badge</li>
                            <li><i class="fas fa-check-circle"></i> +15% Bonus Tokens</li>
                            <li><i class="fas fa-check-circle"></i> Quarterly Reports</li>
                        </ul>
                        <button class="card-button">Select Plan</button>
                    </div>
                </div>
                
                <!-- Gold Tier -->
                <div class="card">
                    <div class="card-header">
                        <div class="card-badge">VIP Benefits</div>
                        <div class="card-icon">
                            <i class="fas fa-medal"></i>
                        </div>
                        <h3 class="card-title">Gold Tier</h3>
                        <div class="card-price">$200+</div>
                        <p class="card-subtitle">For serious gold investors</p>
                    </div>
                    <div class="card-body">
                        <ul class="card-features">
                            <li><i class="fas fa-check-circle"></i> 100+ GRT Tokens</li>
                            <li><i class="fas fa-check-circle"></i> VIP Support</li>
                            <li><i class="fas fa-check-circle"></i> Gold NFT Certificate</li>
                            <li><i class="fas fa-check-circle"></i> Governance Voting Rights</li>
                            <li><i class="fas fa-check-circle"></i> +30% Bonus Tokens</li>
                            <li><i class="fas fa-check-circle"></i> Exclusive Events</li>
                            <li><i class="fas fa-check-circle"></i> Physical Gold Redemption</li>
                        </ul>
                        <button class="card-button">Go Premium</button>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Presale Section -->
    <section id="presale" class="presale-section">
        <div class="container">
            <div class="section-title">
                <h2>Token Presale</h2>
                <p>Join our presale with exclusive pricing and bonuses</p>
            </div>
            
            <div class="presale-container">
                <div class="presale-header">
                    <h3>Presale Ends In:</h3>
                    <div class="countdown">
                        <div class="countdown-box">
                            <div class="countdown-value" id="days">07</div>
                            <div class="countdown-label">Days</div>
                        </div>
                        <div class="countdown-box">
                            <div class="countdown-value" id="hours">16</div>
                            <div class="countdown-label">Hours</div>
                        </div>
                        <div class="countdown-box">
                            <div class="countdown-value" id="minutes">45</div>
                            <div class="countdown-label">Minutes</div>
                        </div>
                        <div class="countdown-box">
                            <div class="countdown-value" id="seconds">30</div>
                            <div class="countdown-label">Seconds</div>
                        </div>
                    </div>
                </div>
                
                <div class="presale-content">
                    <div class="presale-info">
                        <h4>Presale Information</h4>
                        <div class="info-item">
                            <span>Token Price:</span>
                            <span class="gold-text">$1.20 per GRT</span>
                        </div>
                        <div class="info-item">
                            <span>Presale Progress:</span>
                            <span>72%</span>
                        </div>
                        <div class="info-item">
                            <span>Tokens Sold:</span>
                            <span>3,600,000 GRT</span>
                        </div>
                        <div class="info-item">
                            <span>Hard Cap:</span>
                            <span>5,000,000 GRT</span>
                        </div>
                        
                        <div class="progress-container">
                            <div class="info-item">
                                <span>Progress:</span>
                                <span>72%</span>
                            </div>
                            <div class="progress-bar">
                                <div class="progress-fill" id="presaleProgress"></div>
                            </div>
                        </div>
                        
                        <h4 style="margin-top: 30px;">Presale Bonuses</h4>
                        <div class="bonus-item">
                            <div>
                                <span>First 24 hours:</span>
                                <div class="bonus-highlight">Limited time only</div>
                            </div>
                            <span class="gold-text">+30% Bonus</span>
                        </div>
                        <div class="bonus-item">
                            <div>
                                <span>Week 1:</span>
                                <div class="bonus-highlight">Ends in 3 days</div>
                            </div>
                            <span class="gold-text">+20% Bonus</span>
                        </div>
                        <div class="bonus-item">
                            <span>Week 2:</span>
                            <span class="gold-text">+15% Bonus</span>
                        </div>
                        <div class="bonus-item">
                            <span>Final week:</span>
                            <span class="gold-text">+10% Bonus</span>
                        </div>
                    </div>
                    
                    <div class="purchase-box">
                        <div class="purchase-header">
                            <div class="purchase-badge">Special Presale Pricing</div>
                            <h4>Buy Tokens</h4>
                        </div>
                        
                        <div class="form-group">
                            <label for="investmentAmount">Investment Amount (USD)</label>
                            <div class="input-group">
                                <input type="number" min="10" value="100" id="investmentAmount" placeholder="$10 minimum">
                                <div class="input-icon">
                                    <i class="fas fa-dollar-sign"></i>
                                </div>
                            </div>
                            <div class="input-info">
                                <span>Min: $10</span>
                                <span>Max: $5,000</span>
                            </div>
                        </div>
                        
                        <div class="form-group">
                            <label for="tokensReceived">You Receive (GRT)</label>
                            <div class="input-group">
                                <input type="text" id="tokensReceived" value="108.33 GRT" readonly>
                                <div class="input-icon">
                                    <i class="fas fa-coins"></i>
                                </div>
                            </div>
                        </div>
                        
                        <div class="summary-box">
                            <div class="summary-item">
                                <span>Token Price:</span>
                                <span>$1.20</span>
                            </div>
                            <div class="summary-item">
                                <span>Estimated Gas Fee:</span>
                                <span class="gold-text">$5-10</span>
                            </div>
                            <div class="summary-item">
                                <span>Bonus Tokens:</span>
                                <span class="gold-text">+30% (Limited Time)</span>
                            </div>
                        </div>
                        
                        <button id="buyTokens" class="btn-purchase">
                            <i class="fas fa-lock"></i> Buy Tokens Securely
                        </button>
                        
                        <p class="terms">By purchasing, you agree to our <a href="#">Terms of Service</a></p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Wallet Connection Modal -->
    <div id="walletModal" class="modal">
        <div class="modal-content">
            <div class="modal-header">
                <h3>Connect Wallet</h3>
                <button class="close-modal">&times;</button>
            </div>
            <div class="modal-body">
                <div class="wallet-option" id="metamaskOption">
                    <div class="wallet-icon">
                        <i class="fab fa-ethereum"></i>
                    </div>
                    <div class="wallet-details">
                        <h4>MetaMask</h4>
                        <p>Connect to your MetaMask Wallet</p>
                    </div>
                </div>
                <div class="wallet-option">
                    <div class="wallet-icon">
                        <i class="fas fa-wallet"></i>
                    </div>
                    <div class="wallet-details">
                        <h4>WalletConnect</h4>
                        <p>Scan with WalletConnect to connect</p>
                    </div>
                </div>
                <div class="wallet-option">
                    <div class="wallet-icon">
                        <i class="fas fa-coins"></i>
                    </div>
                    <div class="wallet-details">
                        <h4>Coinbase Wallet</h4>
                        <p>Connect to your Coinbase Wallet</p>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Notification -->
    <div id="notification" class="notification">
        <i class="fas fa-check-circle"></i>
        <span id="notificationText">Wallet connected successfully!</span>
    </div>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-grid">
                <div class="footer-col footer-about">
                    <div class="footer-logo">
                        <div class="logo-icon">
                            <i class="fas fa-coins"></i>
                        </div>
                        <h3>GOLD RESERVE TOKEN</h3>
                    </div>
                    <p>Making gold investment accessible and affordable through blockchain technology.</p>
                    <div class="social-links">
                        <a href="#" class="social-link"><i class="fab fa-telegram"></i></a>
                        <a href="#" class="social-link"><i class="fab fa-twitter"></i></a>
                        <a href="#" class="social-link"><i class="fab fa-discord"></i></a>
                        <a href="#" class="social-link"><i class="fab fa-medium"></i></a>
                    </div>
                </div>
                
                <div class="footer-col">
                    <h4>Resources</h4>
                    <ul class="footer-links">
                        <li><a href="#presale">Presale</a></li>
                        <li><a href="#investment">Investment Plans</a></li>
                        <li><a href="#benefits">Benefits</a></li>
                        <li><a href="#security">Security</a></li>
                        <li><a href="#faq">FAQ</a></li>
                    </ul>
                </div>
                
                <div class="footer-col">
                    <h4>Legal</h4>
                    <ul class="footer-links">
                        <li><a href="#">Terms of Service</a></li>
                        <li><a href="#">Privacy Policy</a></li>
                        <li><a href="#">Disclaimer</a></li>
                        <li><a href="#">Audit Reports</a></li>
                    </ul>
                </div>
                
                <div class="footer-col">
                    <h4>Contact</h4>
                    <ul class="contact-info">
                        <li>
                            <i class="fas fa-envelope"></i>
                            <span>contact@goldreservetoken.io</span>
                        </li>
                        <li>
                            <i class="fab fa-telegram"></i>
                            <span>t.me/GoldReserveToken</span>
                        </li>
                        <li>
                            <i class="fab fa-twitter"></i>
                            <span>@GoldReserveToken</span>
                        </li>
                    </ul>
                </div>
            </div>
            
            <div class="footer-bottom">
                <p>© 2024 Gold Reserve Token. All rights reserved.</p>
                <p>This website is for demonstration purposes only. Cryptocurrency investments are volatile and high risk. Always do your own research.</p>
            </div>
        </div>
    </footer>

    <script>
        // DOM Elements
        const connectWalletBtn = document.getElementById('connectWallet');
        const walletText = document.getElementById('walletText');
        const walletModal = document.getElementById('walletModal');
        const closeModal = document.querySelector('.close-modal');
        const metamaskOption = document.getElementById('metamaskOption');
        const buyTokensBtn = document.getElementById('buyTokens');
        const investmentInput = document.getElementById('investmentAmount');
        const tokensOutput = document.getElementById('tokensReceived');
        const notification = document.getElementById('notification');
        const notificationText = document.getElementById('notificationText');
        
        // Wallet connection state
        let walletConnected = false;
        let walletAddress = '';
        
        // Initialize Web3
        let web3;
        if (typeof window.ethereum !== 'undefined') {
            web3 = new Web3(window.ethereum);
        } else {
            console.log('Web3 not detected. Please install MetaMask');
        }
        
        // Connect Wallet Functionality
        connectWalletBtn.addEventListener('click', async () => {
            if (walletConnected) return;
            
            if (typeof window.ethereum !== 'undefined') {
                walletModal.style.display = 'flex';
            } else {
                showNotification('Please install MetaMask!', 'error');
            }
        });
        
        // Close Modal
        closeModal.addEventListener('click', () => {
            walletModal.style.display = 'none';
        });
        
        // Connect with MetaMask
        metamaskOption.addEventListener('click', async () => {
            try {
                const accounts = await window.ethereum.request({ method: 'eth_requestAccounts' });
                walletAddress = accounts[0];
                walletConnected = true;
                
                // Update UI
                const shortenedAddress = walletAddress.substring(0, 6) + '...' + walletAddress.substring(walletAddress.length - 4);
                walletText.textContent = shortenedAddress;
                connectWalletBtn.classList.add('connected');
                
                // Close modal
                walletModal.style.display = 'none';
                
                // Show success notification
                showNotification('Wallet connected successfully!', 'success');
                
                console.log('Connected with address:', walletAddress);
            } catch (error) {
                console.error('Error connecting wallet:', error);
                showNotification('Error connecting wallet', 'error');
            }
        });
        
        // Token Calculator
        investmentInput.addEventListener('input', () => {
            const amount = parseFloat(investmentInput.value) || 0;
            const tokenPrice = 1.20;
            const bonus = 0.30; // 30% bonus
            
            if (amount >= 10 && amount <= 5000) {
                const tokens = (amount / tokenPrice) * (1 + bonus);
                tokensOutput.value = tokens.toFixed(2) + ' GRT';
            } else if (amount < 10) {
                tokensOutput.value = 'Min $10 investment';
            } else {
                tokensOutput.value = 'Max $5,000 investment';
            }
        });
        
        // Buy Tokens Functionality
        buyTokensBtn.addEventListener('click', async () => {
            if (!walletConnected) {
                showNotification('Please connect your wallet first!', 'error');
                return;
            }
            
            const amount = parseFloat(investmentInput.value);
            
            if (isNaN(amount) {
                showNotification('Please enter a valid amount', 'error');
                return;
            }
            
            if (amount < 10) {
                showNotification('Minimum investment is $10', 'error');
                return;
            }
            
            if (amount > 5000) {
                showNotification('Maximum investment is $5,000', 'error');
                return;
            }
            
            // Show processing state
            buyTokensBtn.innerHTML = '<i class="fas fa-spinner fa-spin"></i> Processing...';
            buyTokensBtn.disabled = true;
            
            // Simulate transaction processing
            setTimeout(() => {
                // Calculate tokens
                const tokenPrice = 1.20;
                const bonus = 0.30;
                const tokens = (amount / tokenPrice) * (1 + bonus);
                
                // Show success notification
                showNotification(`Success! ${tokens.toFixed(2)} GRT purchased.`, 'success');
                
                // Reset button
                buyTokensBtn.innerHTML = '<i class="fas fa-lock"></i> Buy Tokens Securely';
                buyTokensBtn.disabled = false;
                
                console.log(`Purchased ${tokens.toFixed(2)} GRT for $${amount}`);
            }, 2000);
        });
        
        // Countdown Timer
        function updateCountdown() {
            const daysEl = document.getElementById('days');
            const hoursEl = document.getElementById('hours');
            const minutesEl = document.getElementById('minutes');
            const secondsEl = document.getElementById('seconds');
            
            // Set target date (7 days from now)
            const targetDate = new Date();
            targetDate.setDate(targetDate.getDate() + 7);
            
            function update() {
                const now = new Date();
                const diff = targetDate - now;
                
                const days = Math.floor(diff / (1000 * 60 * 60 * 24));
                const hours = Math.floor((diff % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
                const minutes = Math.floor((diff % (1000 * 60 * 60)) / (1000 * 60));
                const seconds = Math.floor((diff % (1000 * 60)) / 1000);
                
                daysEl.textContent = days.toString().padStart(2, '0');
                hoursEl.textContent = hours.toString().padStart(2, '0');
                minutesEl.textContent = minutes.toString().padStart(2, '0');
                secondsEl.textContent = seconds.toString().padStart(2, '0');
            }
            
            update();
            setInterval(update, 1000);
        }
        
        // Progress bar animation
        function animateProgressBar() {
            const progressBar = document.getElementById('presaleProgress');
            let width = 0;
            const targetWidth = 72;
            const interval = setInterval(() => {
                if (width >= targetWidth) {
                    clearInterval(interval);
                } else {
                    width++;
                    progressBar.style.width = width + '%';
                }
            }, 20);
        }
        
        // Notification function
        function showNotification(message, type) {
            notificationText.textContent = message;
            notification.className = 'notification show ' + type;
            
            setTimeout(() => {
                notification.classList.remove('show');
            }, 3000);
        }
        
        // Initialize functions
        document.addEventListener('DOMContentLoaded', () => {
            updateCountdown();
            animateProgressBar();
            
            // Smooth scrolling for anchor links
            document.querySelectorAll('a[href^="#"]').forEach(anchor => {
                anchor.addEventListener('click', function(e) {
                    e.preventDefault();
                    
                    const targetId = this.getAttribute('href');
                    if (targetId === '#') return;
                    
                    const targetElement = document.querySelector(targetId);
                    if (targetElement) {
                        window.scrollTo({
                            top: targetElement.offsetTop - 80,
                            behavior: 'smooth'
                        });
                    }
                });
            });
        });
    </script>
</body>
</html>
