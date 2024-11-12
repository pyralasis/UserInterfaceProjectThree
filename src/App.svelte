<script>
  import QuickControls from "./lib/QuickControls.svelte";

  let today = new Date();
  let hours24 = today.getHours();
  let meridian = hours24 > 12 ? "PM" : "AM";
  let hours12 = hours24 != 12 ? hours24 % 12 : 12;
  let min = today.getMinutes();
  let sec = today.getSeconds();
  let month = today.getMonth() + 1;
  let year = today.getFullYear();
  let date = today.getDate();
  let clock = () => {
        today = new Date();
        hours24 = today.getHours();
        meridian = hours24 > 12 ? "PM" : "AM";
        hours12 = Number(today.getHours().toLocaleString()) % 12 || 12;
        min = today.getMinutes();
        sec = today.getSeconds();
        date = today.getDate();
        month = today.getMonth() + 1;
        year = today.getFullYear();

        setTimeout(clock, 1000);
    };
    $: {
        clock();
    }

</script>

<main>
  <div id="TopBar">
    <p>{month}/{date}/{year} {hours24}:{min.toString().padStart(2, "0")} {meridian} 57%</p>
  </div>

  <div class="mainContainer">
    <div id="LeftControls">
      <QuickControls></QuickControls>
    </div>

    <div id="RightControls">
      <!-- Zach: I had this here to hopefully set up the display but I just can't figure it out lol-->
      <h1>placeholder</h1>
    </div>
  </div>
</main>

<style>
  *{
    margin: 0;
    padding: 0;
  }

  #TopBar {
    position: fixed;
    top: 0px;
    left: 0px;
  }

  .mainContainer {
    display: flex;
    flex-direction: row;
    justify-content: left;
  }
  .mainContainer div {
    justify-content: left;
  }
</style>
