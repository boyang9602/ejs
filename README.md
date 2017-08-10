# ejs
modified ejs.min.js to support a new feature  

## tags
Originally, it only supported these tags below:  
`<%` 'Scriptlet' tag, for control-flow, no output  
`<%=` Outputs the value into the template (escaped)  
`<%#` Comment tag, no execution, no output  
`<%%` Outputs a literal `<%`  
`%%>` Outputs a literal `%>`  
`%>` Plain ending tag  
  
Now it supports `-%>` which can eliminate the blank line that this line leaves in the generated file.  
(It will ignore anything from `<% ... -%>` to the first `\n` after it.)  
eg:  
`<% if(true) {-%>`  
`hello`  
`<% } -%>`  
will generate  
hello  
However if you use `<% ... %>` instead of `<% ... -%>`  
it will generate  
[blank line]  
hello  
[blank line]  
