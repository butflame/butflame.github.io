---
title: 百万计划
layout: page
permalink: /millionaire/
hidden_in_header: true
---

<table>
  <caption>
    我们的目标是在捣捣4岁生日时手握百万
  </caption>
  <thead>
    <tr>
      <th>日期</th>
      <th>目标金额</th>
      <th>当前金额</th>
      <th>达成率</th>
      <th>备注</th>
    </tr>
  </thead>
  <tbody>
    {% for month in site.data.millionaire %}
      <tr>
        <th>{{ month.date }}</th>
        <td>{{ month.target }}</td>
        <td>{{ month.current }}</td>
        {% if month.diff >= 0 %}
          <td style="color:green" >{{ month.diff }}</td>
        {% else %}
          <td style="color:red" >{{ month.diff }}</td>
        {% endif %}
        <td>{{ month.remark }}</td>
      </tr>
    {% endfor %}
  </tbody>
</table>
