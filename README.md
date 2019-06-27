# Alfred Phone Number Cleaner
A workflow to remove non-digit characters from a phone number on the clipboard. I occasionally run into on-line forms that want just the digits of phone numbers. 

![workflow](https://github.com/woodwerk/alfred_phone_number_cleaner/blob/master/alfred_phone_number_cleaner_workflow.png?raw=true)

Often, the source for the numbers is in one of several formats such as:

  (456) 321-7890
  
  456-321-7890
  
  456.321.7890
  
  +1 456-321-7890

This workflow uses a clumsy implementation of SED to remove dashes, space, parentheses and the +1 country code from the text on the clipboard.

```
phone="{query}"

echo -n $(echo $phone | sed -e 's/\(\+1\)//g' -e 's/-//g' -e 's/ //g' -e 's/)//g' -e 's/(//g' -e 's/\.//g')
```


  
  
  


