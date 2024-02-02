---
title: Whitespace control
---

# Whitespace control

Trong Liquid, bạn có thể thêm kí tự `-` vào các tag mở đóng như `{{-` và `-}}` hoặc `{%-` và `-%}` để loại bỏ khoảng trống của giá trị hoặc biểu thức mà Liquid tạo ra.
Kí tự này được gọi là hyphen.

Thông thường, kể cả khi biểu thức ko render giá trị nào cả trên một dòng, Liquid vẫn sẽ chừa ra khoảng trống cho dòng đó đó.

```liquid title="Input"
{% assign my_variable = "tomato" %}
{{ my_variable }}
```

Chú ý khoảng trống nằm trên từ "tomato" sau khi render:

```liquid title="Output"

tomato
```

Bằng cách thêm một hyphen vào trong biểu thức, bạn có thể loại bỏ khoảng trống trên.

```liquid title="Input"
{% assign my_variable = "tomato" -%}
{{ my_variable }}
```

```liquid title="Output"
tomato
```

Như thường lệ, bạn nên thêm `{%-` và `-%}` mỗi khi viết một tag để tránh tạo ra các khoảng trống.

```liquid title="Input"
{% assign username = "John G. Chalmers-Smith" %}
{% if username and username.size > 10 %}
  Wow, {{ username }} , you have a long name!
{% else %}
  Hello there!
{% endif %}
```

```liquid title="Output khi không có whitespace control"


  Wow, John G. Chalmers-Smith , you have a long name!
```

```liquid title="Input"
{% assign username = "John G. Chalmers-Smith" -%}
{%- if username and username.size > 10 -%}
  Wow, {{ username -}} , you have a long name!
{%- else -%}
  Hello there!
{%- endif %}
```

```liquid title="Output khi có whitespace control"
  Wow, John G. Chalmers-Smith , you have a long name!
```
