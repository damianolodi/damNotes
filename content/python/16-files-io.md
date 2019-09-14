---
title: "Files I/O"
draft: false
weight: 16
---

```py
import csv
```

### Read CSV files

```py
with open('data.csv','r') as csv_file:
    csv_reader = csv.reader(csv_file, delimiter=' ')

    next(csv_reader)        # skip over the header line

    for line in csv_reader:
        print(line)
```

- use `with` to automatically close the file at the end

### Write on CSV files

```py
with open('new_file.csv','w') as new_file:
    csv_writer = csv.writer(new_file, delimiter='\t')

    for line in csv_reader:
        csv_writer.writerow(something)
```

- use `w+` to create the file if it does not exist

### Reading with Dictionary Reader

Use if more "human readable" files are needed

```py
with open('data.csv','r') as csv_file:
    csv_reader = csv.DictReader(csv_file,delimiter=' ')

    for line in csv_reader:
        print(line)
```

### Writing with Dictionary Writer

```py
with open('data.csv','r') as csv_file:
    csv_reader = csv.DictReader(csv_file,delimiter=' ')
    
    with open('new_file.csv','w') as new_file:
        field_names = ['data','ora','bo1','bo2','bo3','bo4','bo5','bo6','bo7','bo8']
        csv_writer = csv.DictWriter(new_file, field_names=field_names, delimiter='\t')
        csv_writer.writeheader()    # write the header in the new file

        for line in csv_reader:
            # skip writing the 'bo1' column
            # del line['bo1'] #delete the 'bo1' in 'field_names'
            csv_writer.writerow(line)
```
