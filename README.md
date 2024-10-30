Powershell function to return the patch Tuesday of the current month.

```powershell
Function Get-PatchTuesday {
  [datetime]$today = [datetime]::NOW
  $todayM = $today.Month.ToString()
  $todayY = $today.Year.ToString()
  [datetime]$strtMonth = $todayM + '/1/' + $todayY
  while ($strtMonth.DayofWeek -ine "Tuesday" ) { $strtMonth = $StrtMonth.AddDays(1) }
  $firstWeekDay = $strtMonth
  $patchTuesday = $firstWeekDay.AddDays(7) 
  return $patchTuesday
}
```
