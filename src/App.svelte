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
  <div class="top">
    <div id="TopBar">
      <p>
        {month}/{date}/{year}
        {hours24}:{min.toString().padStart(2, "0")}
        {meridian} 90%
      </p>
      <img src="battery.png" height="25" width="25" alt="battery icon" />
    </div>

    <div class="mainContainer">
      <div class="maintenance"></div>
      <img alt="maintenance icons" src="maintenance icons.png" />
      <div id="LeftControls">
        <QuickControls></QuickControls>
      </div>

      <div id="RightControls">
        <!-- Zach: I had this here to hopefully set up the display but I just can't figure it out lol-->
        <iframe
          title="navigation"
          src="https://www.google.com/maps/embed?pb=!1m14!1m8!1m3!1d164388.20990939497!2d-84.52020278550863!3d39.13106191862196!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x8841b38acb65ec25%3A0x4249b42781c0c5fc!2sUniversity%20of%20Cincinnati!5e1!3m2!1sen!2sus!4v1731696240570!5m2!1sen!2sus"
          width="800"
          height="700"
          style="border:0;"
          loading="lazy"
          referrerpolicy="no-referrer-when-downgrade"
        ></iframe>
      </div>
    </div>
  </div>
</main>

<style>
  * {
    margin: 0;
    padding: 0;
  }

  .top {
    display: flex;
    flex-direction: column;
    justify-content: left;
    align-items: left;
  }

  #TopBar {
    /* position: fixed;
    top: 0px;
    left: 0px; */
    border: 1px solid black;
    display: flex;
    justify-content: flex-start;
    gap: 10px;
  }

  .mainContainer {
    display: flex;
    flex-direction: row;
    justify-content: left;
    border: 1px solid black;
  }
  .mainContainer div {
    justify-content: left;
  }
  main {
    display: flex;
    flex-direction: column;
  }

  #LeftControls,
  #RightControls {
    border: 1px solid black;
    /* width: 5rem; */
  }
  #LeftControls {
    width: 300px;
  }
</style>
