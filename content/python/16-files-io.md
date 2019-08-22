# Files I/O

Use

```py
import csv
```

in your program.

## SIMPLE READ .CSV FILE

Use `with` to automatically close the file at the end

```py
with open('data.csv','r') as csv_file:
    csv_reader = csv.reader(csv_file, delimiter=' ')

    # to skip over the header line
    next(csv_reader)

    for line in csv_reader:
        print(line)
```

## SIMPLE WRITE ON A NEW .CSV FILE

```py
with open('data.csv','r') as csv_file:
    csv_reader = csv.reader(csv_file, delimiter=' ')
    # open a new file
    with open('new_file.csv','w') as new_file:
        csv_writer = csv.writer(new_file, delimiter='\t')

        for line in csv_reader:
            csv_writer.writerow(line)
```

## READING WITH DICTIONARY READER

Use dictionary reader if you want more "human readable" files

```py
with open('data.csv','r') as csv_file:
    csv_reader = csv.DictReader(csv_file,delimiter=' ')

    for line in csv_reader:
        print(line)
        #print only the time
        #print(line['ora'])
```

## WRITING WITH DICTIONARY WRITER

```py
with open('data.csv','r') as csv_file:
    csv_reader = csv.DictReader(csv_file,delimiter=' ')
    # open a new file
    with open('new_file.csv','w') as new_file:
        # create the list of filednames
        fieldnames = ['data','ora','bo1','bo2','bo3','bo4','bo5','bo6','bo7','bo8']
        csv_writer = csv.DictWriter(new_file, fieldnames=fieldnames, delimiter='\t')
        #write the header in the new file
        csv_writer.writeheader()

        for line in csv_reader:
            # skip writing the 'bo1' column
            # del line['bo1'] #delete the 'bo1' in 'fieldnames'
            csv_writer.writerow(line)
```
