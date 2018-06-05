## Margin collapse

Today I found out about margin collapse. This is when if you have 2 elements next to each other with some sort of margin applied. The one that has a larger margin will take precedence. For example, element 1 has margin-bottom of 25px and element 2 has margin-top of 20px. Element 1 is on top of element 2. You would normally expect the total margin between element 1 and 2 to be 45px however it would actually be 25px as element 1 margin is larger therefore takes priority. 
