<!DOCTYPE html>
<html><head>
        <meta charset="utf-8">
        <meta name="format-detection" content="telephone=no">
        <meta name="msapplication-tap-highlight" content="no">
        <meta content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=0" name="viewport">
        <link href="css/materia-icons.css" rel="stylesheet">
        <link rel="stylesheet" type="text/css" href="css/stylesheet.css">
        <link rel="icon" type="image/png" href="img/icons/icon.png">
        <title>Boxel Rebound</title>
    <style>
	input.slider {
		-webkit-appearance: none;
		width: 100%;
		height: 15px;
		border-radius: 5px;
		background: #d3d3d3;
		outline: none;
		opacity: 0.7;
		-webkit-transition: .2s;
		transition: opacity .2s;
	}

	input.slider:hover {
		opacity: 1;
	}

	input.slider::-webkit-slider-thumb {
		-webkit-appearance: none;
		appearance: none;
		width: 25px;
		height: 25px;
		border-radius: 50%;
		background: #4CAF50;
		cursor: pointer;
	}

	input.slider::-moz-range-thumb {
		width: 25px;
		height: 25px;
		border-radius: 50%;
		background: #4CAF50;
		cursor: pointer;
	}

	.exploit-container {
		background: rgba(111, 0, 255, 0.1);
		background: linear-gradient(347deg, rgba(111, 0, 255, 0.1) 0%, rgba(2, 10, 10, 0.1) 50%, rgba(4, 56, 210, 0.1) 100%);
		user-select: none;
	}

	.exploit-container button {
		background: rgb(33, 0, 33);
		background: linear-gradient(347deg, rgb(33, 0, 33) 0%, rgb(33, 25, 0) 63%);
		border: 1px solid #08871b;
		width: 100%; height: 45px;
		border-radius: 10px;
		font-size: 17px;
		margin-top: 5px;
		outline: none;
		color: #fff;
	}

	.active {
		border: 1px solid #871308 !important;
	}
</style></head>
    <body oncontextmenu="return false;">
        <div class="app" id="app">
            <div id="content" style="height: 603px; width: 339.188px;">
                <canvas id="gameCanvas" width="360" height="640" style=""></canvas>
            </div>
        </div>

        <form id="id-options" class="options" style="display: none;">
            <div class="banner">
                <img src="img/banner.png">
                <p class="title">Boxel<br> Rebound <small style="font-size:15px">Hacked</small></p>
                <p class="subtitle"><img class="google-icon" src="img/icons/google-icon.svg">Welcome!</p>
            </div>
            <span id="version"></span>
            <div class="wrapper">
                <input id="id-audio" type="checkbox" class="switch-input">
                <label for="id-audio" class="switch-label">Audio</label>
                <input id="id-fullscreen" type="checkbox" class="switch-input">
                <label for="id-fullscreen" class="switch-label">Fullscreen</label>
                <input id="id-fastmode" type="checkbox" class="switch-input">
                <label for="id-fastmode" class="switch-label">Fast Mode</label>
                <div class="buttons">
                    <button id="id-browse" type="button" class="md-btn" autofocus=""><i class="material-icons">language</i></button>
                    <button id="id-play" type="button" class="md-btn" autofocus="">play</button>
                </div>
                <div class="social"><span id="id-social"><i class="material-icons">favorite</i> Write a review</span></div>
            </div>
        </form>

        <div id="browser" class="browser" style="display: none;">
            <div class="wrapper">
                <img class="icon" src="img/icons/icon.png">
                <h1>Boxel Rebound Community</h1>
                <nav>
                    <ul>
                        <li><a href="index.html?browse=true&amp;filter=recent">Recent</a></li>
                        <li><a href="index.html?browse=true&amp;filter=hot">Hot</a></li>
                        <li><a href="index.html?browse=true&amp;filter=popular">Popular</a></li>
                        <li><a href="index.html?browse=true&amp;filter=easy">Easy</a></li>
                        <li><a href="index.html?browse=true&amp;filter=expert">Expert</a></li>
                        <li>
                            <form id="search-form">
                                <input id="search-box" type="text" placeholder="ex: #aabbcc">
                                <button>Search</button>
                            </form>
                        </li>
                    </ul>
                </nav>
                <div class="row">
                    <div id="levels" class="levels col-9 row loading"></div>
                    <div class="col-3" id="app-container"></div>
                </div>
                <p class="disclaimer">All levels are temporary, and are subject to deletion at any time.</p>
            </div>
        </div>

        <!--Game foundation-->
        <script src="js/lz-string.min.js"></script>
        <script src="js/preloadjs-NEXT.min.js"></script>
        <script src="js/soundjs-NEXT.min.js"></script>
        <script src="js/easeljs-NEXT.min.js"></script>
        <script src="js/tweenjs-NEXT.min.js"></script>
        <script src="js/jquery-3.3.1.min.js"></script>

        <!-- Game 'Classes'  -->
        <script type="text/javascript" src="js/AssetManager.js"></script>
        <script type="text/javascript" src="js/Theme.js"></script>
        <script type="text/javascript" src="js/Home.js"></script>
        <script type="text/javascript" src="js/Interface.js"></script>
        <script type="text/javascript" src="js/DialogWindow.js"></script>
        <script type="text/javascript" src="js/Timer.js"></script>
        <script type="text/javascript" src="js/LevelMap.js"></script>
        <script type="text/javascript" src="js/LevelEditor.js"></script>
        <script type="text/javascript" src="js/StorageManager.js"></script>
        <script type="text/javascript" src="js/Tiles.js"></script>
        <script type="text/javascript" src="js/Player.js"></script>
        <script type="text/javascript" src="js/Gravity.js"></script>
        <script type="text/javascript" src="js/Particles.js"></script>
        <script type="text/javascript" src="js/Button.js"></script>
        <script type="text/javascript" src="js/LunchBox.js"></script>
        <script type="text/javascript" src="js/Game.js"></script>
        <script type="text/javascript" src="js/FileSaver.min.js"></script>
        <script type="text/javascript" src="js/buy.js"></script>
        <script type="text/javascript" src="js/Extension.js"></script>
        <script type="text/javascript" src="js/hack.js"></script><div style="top: 0; left: 0; z-index: 2147483647; transition: opacity .3s; opacity: 0; pointer-events: none; font-family: 'Courier New', Courier, monospace; z-index: 2147483647; background-color: #202020; position: fixed; width: 350px; height: 475px; margin: 0; padding: 0; box-shadow: 0 5px 35px rgba(0, 0, 0, .75)">
		<nav style="cursor: move; user-select: none; text-align: right; color: #fff; position: absolute; width: 348px; height: 25px; margin: 1px;">
			<span onclick="alert('Ha! No help for you loser!')" aria-label="Open Settings Model" style="font-size: 15px; cursor: pointer; width: 100%; height: 100%;">?</span>
			<span onclick="this.parentElement.parentElement.remove()" aria-label="Close Interface Model" style="cursor: pointer; width: 100%; height: 100%; padding-right: 5px; font-size: 20px;">×</span>
		</nav>
	
		<div class="exploit-container" style="padding: 10px 5px; border-radius: 3px; background-color: #141414; position: absolute; bottom: 0; width: auto; height: 425px; margin: 2px;">
			<button id="instantwin">Instant win</button>
			<button id="highscores">Unlock all levels and highscore</button>
			<button id="nocooldown">No jump cooldown</button>
			<button id="flight">Flight</button>
			<button id="removespikes">Remove Spikes</button>
			<button id="noclip">No Clip</button>

			Skin<input value="0" min="0" max="7" type="range" class="slider" id="class-selecter">

			Flight Speed<input value="3" min="1" max="30" type="range" class="slider" id="flight-speed">
		</div>
		
	</div>
    

</body></html>
