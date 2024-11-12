<script>
    let frontLeftTirePressure = 32;
    let frontRightTirePressure = 30;
    let backLeftTirePressure = 31;
    let backRightTirePRessure = 32;
</script>

<div id="AllControls">
    <div id="QuickControls">
        <h3>Quick Controls</h3>

    </div>

    <div id="CarStats">
        <h3>Tire Pressure (psi):</h3>
        <p>Front Left:{frontLeftTirePressure} Front Right:{frontRightTirePressure}</p>
        <p>Back Left:{backLeftTirePressure} Back Right:{backRightTirePRessure}</p>

        <h3>Odomoter: 27521mi</h3>
    </div>
</div>

<style>
    #AllControls {
        display: flex;
        flex-direction: column;
    }
</style>