---
title: Variable
---

# Variable

Các variable tags cho phép tạo ra khác biến mới trong Liquid.

## assign

Tạo mới biến.

```liquid title="Input"
{% assign my_variable = false %}
{% if my_variable != true %}
  This statement is valid.
{% endif %}
```

```html title="Output"
This statement is valid.
```

Thêm kí tự `"` để lưu giá trị dưới dạng một string.

```liquid title="Input"
{% assign foo = "bar" %}
{{ foo }}
```

```html title="Output"

bar
```

## capture

Gán toàn bộ nội dung sau thẻ mở và trước thẻ đóng của tag `capture`. Những biến được khởi tạo bởi `capture` sẽ lưu nội dung dưới dạng string.

```liquid title="Input"
{% capture my_variable %}I am being captured.{% endcapture %}
{{ my_variable }}
```

```html title="Output"
I am being captured.
```

Bạn cũng có thể sử dụng giá trị các biến khác của liquid trong nội dung của `capture`. 

```liquid title="Input"
{% assign favorite_food = "pizza" %}
{% assign age = 35 %}

{% capture about_me %}
I am {{ age }} and my favorite food is {{ favorite_food }}.
{% endcapture %}

{{ about_me }}
```

```html title="Output"
I am 35 and my favourite food is pizza.
```

## increment

Khởi tạo và hiển thị biến với giá trị mới bắt đầu từ 0. Ở những lần gọi tiếp theo, giá trị của biến sẽ được tăng thêm 1 đơn vị và hiển thị ra ngoài template.

```liquid title="Input"
{% increment my_counter %}
{% increment my_counter %}
{% increment my_counter %}
```

```html title="Output"
0
1
2
```

:::note
Biến được khởi tạo bởi `increment` hoạt động **độc lập** so với biến được khai báo bởi `assign` hoặc `capture` cùng tên.

Ở ví dụ phía dưới, một biến có tên `"var"` được khởi tạo thông qua `assign`. Tiếp đó là các tag `increment` thực hiện liên tiếp phép tăng 1 đơn vị với cùng một tên biến trước đó. Chú ý trong trường hợp này, mặc dù cả 2 biến được khởi tạo giữa 2 tag `assign` và `increment` là như nhau, nhưng giá trị của biến `"var"` được khai báo bởi `assign` không bị ảnh hưởng bởi các dòng lệnh `increment`, do đó giá trị của `"var"` vẫn được bảo toàn.

```liquid title="Input"
{% assign var = 10 %}
{% increment var %}
{% increment var %}
{% increment var %}
{{ var }}
```

```html title="Output"

0
1
2
10
```
:::