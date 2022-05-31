# auto-administration

This is multiple-citys-react components，Support multiple selection components of provinces and cities（自动化招聘）
## first step
```
  打开浏览器，按下f12

```
## second step
 将下面代码放进去，并执行
```
<script src="http://code.jquery.com/jquery-migrate-1.2.1.min.js"></script>

```

### third step

打开index.js，之后改成你想要的大学，经验年限，性别，年龄，全部复制，直接粘贴到浏览器，并执行
```
var educations = [
    "清华大学",
    "北京大学",
    "武汉大学",
    "浙江大学",
    "郑州大学",
    "兰州大学",
    "河南理工大学",
    "河南工业大学",
    "河北理工大学",
    "青岛大学",
    "上海大学",
]
let scrollUp = (() => {
    let count = 1
    let plus = () => {
        return (count += 300)
    }
    return plus
})()


const findWantedWithAutoClick = (sex, age, educations, years) => {
    if (Array.isArray($('.boss-list-item'))) {


        $('.boss-list-item').each((item) => {

            if (Number(($(this).find('boss-list-itemage').text()) < age
                && $(this).find('boss-list-itemsex').text() === sex
                && Number(($(this).find('boss-list-itemyears').text()) > years
                    && educations.includes((this).find('boss-list-itemeducation').text())
                ){

                $(this).trigger('click')
            }
        })
    }
}


window.setInterval(() => {
    window.scrollTo(0, scrollUp())
    findWantedWithAutoClick("男", 35, educations, 5)
}, 3000)




```
好了，剩下的交给程序，你不用一个一个找候选人了，可以去洗脚泡妞去了
