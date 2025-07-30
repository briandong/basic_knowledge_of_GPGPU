
# Markdown语法

## 标题

```markdown
# Heading 1
## Heading 2
### Heading 3
#### Heading 4
##### Heading 5
###### Heading 6
```
# Heading 1
## Heading 2
### Heading 3
#### Heading 4
##### Heading 5
###### Heading 6

## 强调

### 粗体

```markdown
this is **bold** text
```
this is **bold** text

### 斜体

```markdown
this is *italic* text
```
this is *italic* text

### 删除线

```markdown
我们知道世界是 ~~平坦~~ 圆的。
```
我们知道世界是 ~~平坦~~ 圆的。

## 引用

### 普通引用
```markdown
> quote
```
> quote

### 嵌套引用
```markdown
> quote level 1
>> quote level 2
```
> quote level 1
>> quote level 2


## 列表
### 无序列表
```markdown
- item a
- item b
- item c
```

- item a
- item b
- item c

### 有序列表
```markdown
1. 1st item
1. 2nd item
1. 3rd item
```

1. 1st item
1. 2nd item
1. 3rd item

### 嵌套列表
```markdown
1. 1st item
1. 2nd item
   - indented item
   - indented item
1. 3rd item
```
1. 1st item
1. 2nd item
   - indented item
   - indented item
1. 3rd item

### 任务列表
```markdown
- [x] Write the press release
- [ ] Update the website
- [ ] Contact the media
```
- [x] Write the press release
- [ ] Update the website
- [ ] Contact the media

## 分隔线

```markdown
---
```
---

## 表格

```markdown
| Syntax      | Description | Test Text     |
| :---        |    :----:   |          ---: |
| Header      | Title       | Here's this   |
| Paragraph   | Text        | And more      |
```
| Syntax      | Description | Test Text     |
| :---        |    :----:   |          ---: |
| Header      | Title       | Here's this   |
| Paragraph   | Text        | And more      |

## 链接

```markdown
这是一个链接 [Markdown语法](https://markdown.com.cn)。
```
这是一个链接 [Markdown语法](https://markdown.com.cn)。

使用尖括号可以很方便地把URL或者email地址变成可点击的链接。
```markdown
<https://markdown.com.cn>  
<fake@example.com>
```
<https://markdown.com.cn>  
<fake@example.com>

## 图片

```markdown
![markdown](./images/markdown.png "Markdown Now!")
```
![markdown](./images/markdown.png "Markdown Now!")
