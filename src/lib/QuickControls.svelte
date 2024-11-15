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
    <div id="NavigationUI">
        <img
            id="NavigationImage"
            src="https://www.tesla.com/ownersmanual/images/GUID-2BE784C9-FDF3-486F-B287-83F7B6BD5FEB-online-en-US.png"
            alt="navigation picture"
        />
    </div>

    <div id="SpotifyControls">
        <img
            id="SongCover"
            src="https://variety.com/wp-content/uploads/2021/07/Rick-Astley-Never-Gonna-Give-You-Up.png"
            alt="album icon"
        />
        <div id="SongInformation">
            <p>Never Gonna Give You Up</p>
            <p>Rick Astley</p>
            <p>Whenever You Need Somebody</p>
            <input type="range" name="" id="" />
        </div>
    </div>
    <div id="QuickControls">
        <h3>Quick Controls</h3>
        <div id="QuickControlButtons">
            <!-- add icons to replace the text for the buttons -->
            <button on:click={radioAlert}
                ><i class="fa-solid fa-radio"></i></button
            >
            <button on:click={gameAlert}
                ><i class="fa-solid fa-gamepad"></i></button
            >
            <button on:click={videoAlert}><i class="fa-solid fa-tv"></i></button
            >
            <button on:click={callingAlert}
                ><i class="fa-solid fa-phone"></i></button
            >
        </div>
    </div>

    <div id="CarStats">
        <h3>Tire Pressure (psi):</h3>
        <p>
            Front Left:{frontLeftTirePressure} Front Right:{frontRightTirePressure}
        </p>
        <p>
            Back Left:{backLeftTirePressure} Back Right:{backRightTirePRessure}
        </p>

        <h3>Odomoter: 27521mi</h3>
        <button on:click={settingsAlert}
            ><i class="fa-solid fa-gear"></i></button
        >
        <button on:click={carAlert}><i class="fa-solid fa-car"></i></button>
    </div>
</div>

<style>
    #AllControls {
        display: flex;
        flex-direction: column;
    }

    #QuickControlButtons {
        display: flex;
        flex-direction: row;
        justify-content: center;
    }

    p {
        margin: 0;
        padding: 0;
    }
    #SongCover {
        width: 25%;
    }
    #SpotifyControls {
        display: flex;
        flex-direction: row;
        justify-content: center;
        border: 1px solid black;
    }
    #NavigationImage {
        width: 25%;
    }
</style>
