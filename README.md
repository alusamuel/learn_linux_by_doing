# learn_linux_by_doing

Task 1:

1. Delete file test-1
> $ rm -r test-1

2.move file to analyze directory
> $ mv top5-highest-temperatures.csv ./analyzed

3.change name files
> $ find ./analyzed -type f ! -name 'top-5*' -exec sh -c 'f="$(basename "$1")"; d="$(dirname "$1")"; mv "$1" "$d/top-5-${f#top5-}"' sh {} \;

Task 2:

1. remove duplicate rows
> $ ort satelite_temperature_data.csv | uniq > satelite_temperature_data.csv

2. Highest temperature
> $ cut -d',' -f1,2,3,4 data/satelite_temperature_data.csv | sort -t',' -k3,3nr | head -n 5 > analyzed/top-5-highest-temperatures.csv

3.Lowest temperature
> $ cut -d',' -f1,2,3,4 data/satelite_temperature_data.csv | sort -t',' -k3,3n | head -n 5 > analyzed/top-5-lowest-temperatures.csv

4.Heat record from your country
> $ grep "Rwanda" data/satelite_temperature_data.csv > analyzed/country-heat_data.csv
