<script lang="ts">
  let count = 0
  let firstDate = '02.01.2022'
  let secondDate = '02.01.2022'

  function isDateValid(date: string): boolean {
    const parts = date.split('.')

    if (parts.length !== 3) {
      return false
    }
    if (!parts.every(part => part)) {
      return false
    }
    const [dayString, monthString, yearString] = parts
    const [day, month, year] = [
      Number.parseInt(dayString),
      Number.parseInt(monthString),
      Number.parseInt(yearString),
    ]

    if (day < 1 || day > 31) {
      return false
    }
    if (month < 1 || month > 12) {
      return false
    }
    if (year < 2000) {
      return false
    }

    return true
  }

</script>

<div>
  <select>
    <option>one-way flight</option>
    <option>return flight</option>
  </select> <br/>
  <input
    type="text"
    bind:value={firstDate}
    style:background-color={isDateValid(firstDate) ? '' : 'red'}
  /> <br/>
  <input
    type="text"
    bind:value={secondDate}
    style:background-color={isDateValid(secondDate) ? '' : 'red'}
  /> <br/>
  <button>Book</button>
</div>
