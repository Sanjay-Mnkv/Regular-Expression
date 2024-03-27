#!/bin/python3
import re
import csv
def extractld(istring):

  letters=''.join(re.findall(r'[a-zA-Z]',istring))
  digits=''.join(re.findall(r'[0-9]',istring))
  return letters,digits
while True:
    print('1.Extract ')
    print('2.Exit')
    ch=input('Enter your choice:')
    if ch=='1':
     istring=input('Enter the string:')
     letters=extractld(istring)
     digits=extractld(istring)
     print(letters)

    elif ch=='2':
     print('exit')   
     
    if ch not in ['1','2']:
     print('invalid')
    with open('ans.csv','a',newline='') as csvfile:
     writer=csv.writer(csvfile)
     writer.writerow(['Extract'])
     writer.writerow([''.join(letters)])
