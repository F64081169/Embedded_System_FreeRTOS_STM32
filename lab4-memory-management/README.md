[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/7xVhK6-x)

# 實作邏輯:
- Step1:宣告一個BlockLink_t的temp，用while loop和temp從xStart走訪free block linked list。並藉由Uart印出每個free block的資訊，其中free block的start address 與 end address分別為指標的位址與指標的位址加上xBlockSize。

- Step2: pxIterator指向Start，pxPrevious指向pxIterator的前一個，利用這兩個與while loop走訪整個linked list。
while loop裡面的if-else判斷邏輯是判斷
  - 1.pxIterator是否等於Blockholding+xBlockSize? 
如果是的話代表可以merge free block : 合併 Blockholding的xBlockSize，pxPrevious更新至pxIterator的下一個block。
  - 2.pxIterator+xBlockSize是否等於Blockholding的start address? 
如果是的話代表可以merge free block : 合併pxIterator的xBlockSize，並將更新後的pxIterator賦值給Blockholding，pxPrevious更新至pxIterator的下一個block。
  - 3.兩者皆不是的話iterate至下一個free block。
