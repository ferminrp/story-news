<script>
  export let date;

  // array of months
  export let months = [
    "January",
    "February",
    "March",
    "April",
    "May",
    "June",
    "July",
    "August",
    "September",
    "October",
    "November",
    "December",
  ];

  const suffixMap = {
    one: "st",
    two: "nd",
    few: "rd",
    other: "th",
  };
  const locale = "en-GB";
  const moment = new Date(date + "T00:00:00Z");
  const dayOfMonth = moment.getDate();
  const month = moment.getMonth();
  let dayString;

  switch (dayOfMonth) {
    case (1, 21, 31):
      dayString = dayOfMonth + "st";
      break;
    case (2, 22):
      dayString = dayOfMonth + "nd";
      break;
    case (3, 23):
        dayString = dayOfMonth + "rd";
        break;
    default:
        dayString = dayOfMonth + "th";
      break;
  }
</script>

<h2>{months[month]+' '+dayString}</h2>

<style>
  h2 {
    font-family: "Lora", serif;
    font-size: 1.2rem;
    margin: 2rem auto;
    max-width: 90vw;
    font-weight: 600;
  }
</style>
