### 关于文字换行
```` css
div {
    overflow: hidden; //BFC
    word-wrap: break-word; //长的url自动换行
    word-break: break-all; //单词短语自动换行
    white-space: nowrap; //这一行不换行
    text-overflow: ellipsis; //超出部分...
}
 ````
