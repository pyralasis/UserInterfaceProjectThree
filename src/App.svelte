<script>
  import QuickControls from "./lib/QuickControls.svelte";
  import "@fortawesome/fontawesome-free/css/all.min.css";

  let today = new Date();
  let hours24 = today.getHours();
  let meridian = hours24 > 12 ? "PM" : "AM";
  let hours12 = hours24 != 12 ? hours24 % 12 : 12;
  let min = today.getMinutes();
  let sec = today.getSeconds();
  let month = today.getMonth() + 1;
  let year = today.getFullYear();
  let date = today.getDate();
  let temp = "46°F"
  let charge = "86"
  let clock = () => {
    today = new Date();
    hours24 = today.getHours();
    meridian = hours24 > 12 ? "PM" : "AM";
    hours12 = Number(today.getHours().toLocaleString()) % 12;
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

<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css"/>

<main>

  <div id="top-bar">
    <inl class="top-bar-elem">{hours12}:{min.toString().padStart(2, "0")} {meridian}</inl>
    <inl class="top-bar-elem">{month}-{date}-{year}</inl>
    <inl class="top-bar-elem">{temp}</inl>
    <inl class="top-bar-elem"><i class="fa-solid fa-bolt"></i> {charge}</inl>
  </div>

  <div class="mainContainer">

    <img alt="maintenance icons" src="maintenance icons.png" width="66" />

    <div id="LeftControls">
      <QuickControls></QuickControls>
    </div>

    <div id="RightControls">
      <!-- Zach: I had this here to hopefully set up the display but I just can't figure it out lol-->
      <iframe
        title="navigation"
        src="https://www.google.com/maps/embed?pb=!1m14!1m8!1m3!1d164388.20990939497!2d-84.52020278550863!3d39.13106191862196!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x8841b38acb65ec25%3A0x4249b42781c0c5fc!2sUniversity%20of%20Cincinnati!5e1!3m2!1sen!2sus!4v1731696240570!5m2!1sen!2sus"
        width="800"
        height="694"
        style="border-radius: 10px; margin-right: 8px"
        loading="lazy"
        referrerpolicy="no-referrer-when-downgrade"
      ></iframe>
    </div>
  </div>

</main>

<style>
  main {
    margin: 0;
    padding: 0;

    font-family: 'Segoe UI', Arial, Helvetica, sans-serif;

    border: 6px solid gray;
    padding: 4px;
    border-radius: 20px;
  }

  #top-bar {
    justify-content: left;
    text-align: left;
    margin-bottom: 4px;
  }

  .top-bar-elem {
    margin: 2px 8px;
    font-size: 16px;
    font-weight: bold;
  }

  .mainContainer {
    display: flex;
    flex-direction: row;
    justify-content: left;
  }

  .mainContainer div {
    justify-content: left;
  }

  #LeftControls {
    width: 300px;
  }
</style>
