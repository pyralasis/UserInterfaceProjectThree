<script>
    import "@fortawesome/fontawesome-free/css/all.min.css";

    let frontLeftTirePressure = 32;
    let frontRightTirePressure = 30;
    let backLeftTirePressure = 31;
    let backRightTirePRessure = 32;

    function radioAlert() {
        window.alert("Clicking this would show the car's radio controls");
    }

    function gameAlert() {
        window.alert("Clicking this would show the car's game controls.");
    }

    function videoAlert() {
        window.alert("Clicking this would show the car's video controls.");
    }

    function callingAlert() {
        window.alert("Clicking this would show the car's calling controls.");
    }

    function settingsAlert() {
        window.alert("Clicking this would show the car's settings menu.");
    }

    function carAlert() {
        window.alert("Clicking this would show the car overview menu.");
    }
</script>

<link
    rel="stylesheet"
    href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css"
/>

<div id="AllControls">
    <div>
        <inl class="nav-speed">12</inl><inl>MPH</inl>
        <inl class="nav-prn">P R N</inl> <inl class="nav-d">D</inl>
        <img class="nav-and-album-img" src="road_view.png" height="250px" width="250px" alt="navigation" />
    </div>

    <div id="music-controls">
        <img src="album.png" height="108" width="108" alt="album" style="display: inline-block" class="nav-and-album-img"/>
        <div style="display: inline-block; vertical-align: top; padding-top: 4px;">
            <b>Wonderwall</b>
            <p>Oasis</p>
            <input type="range" name="" id="" /><br>
            <i class="fa-solid fa-play" style="margin: 0 4px;"></i>
            <i class="fa-solid fa-backward" style="margin: 0 4px;"></i>
            <i class="fa-solid fa-forward" style="margin: 0 4px;"></i>
            <i class="fa-brands fa-bluetooth" style="margin: 0 4px;"></i>
        </div>
    </div>
    <div>
        <div class="quick-control-row">
            <button on:click={callingAlert} class="quick-btn"><i class="fa-solid fa-phone"></i></button>
            <button on:click={settingsAlert} class="quick-btn"><i class="fa-solid fa-gear"></i></button>
            <button on:click={carAlert} class="quick-btn"><i class="fa-solid fa-car"></i></button>
        </div>
        <div class="quick-control-row">
            <button on:click={radioAlert} class="quick-btn"><i class="fa-solid fa-radio"></i></button>
            <button on:click={gameAlert} class="quick-btn"><i class="fa-solid fa-gamepad"></i></button>
            <button on:click={videoAlert} class="quick-btn"><i class="fa-solid fa-tv"></i></button>
        </div>
    </div>

    <div id="car-stats">
        <p>Until Next Charge <b>402</b> <inl style="font-size: 12px; color: gray">miles</inl></p>
        <p>Odomoter (Trip) <b>27521</b> (20) <inl style="font-size: 12px; color: gray">miles</inl></p>
        <p>
            Front L <b>{frontLeftTirePressure} </b><inl class="units">psi</inl> Front R <b>{frontRightTirePressure} </b><inl class="units">psi</inl>
        </p>
        <p>
            Rear L <b>{backLeftTirePressure} </b><inl class="units">psi</inl> Rear R <b>{backRightTirePRessure} </b><inl class="units">psi</inl>
        </p>
    </div>
</div>

<style>

    .nav-speed {
        font-size: 42px;
        font-weight: bolder;
    }

    .nav-prn {
        color: gray;
        margin-left: 40px;
        font-size: 18px;
    }

    .nav-d {
        font-weight: bolder;
        font-size: 18px;
    }

    .nav-and-album-img {
        border-radius: 12px;
    }

    #music-controls {
        min-height: 108px;
        margin-top: 12px;
    }

    #AllControls {
        display: flex;
        flex-direction: column;
    }

    .quick-control-row {
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-content: center;
        margin-top: 8px;
    }

    .quick-btn {
        min-width: 72px;
        min-height: 56px;
        margin: 4px 8px;
        font-size: 18px
    }

    .units {
        font-size: 12px;
        color: gray;
    }

    #car-stats {
        margin-top: 10px;
    }

    p {
        margin: 0;
        padding: 0;
    }
</style>
