<tr>
  <td><a href="{{ person.url }}">{{ person.title}}</a>

{% if include.short!='short' %}
</td>
<td>
{% endif %}

{% if person.tags contains 'member' %}
&nbsp; &nbsp; NPPS member
{% endif %}

{% if person.tags contains 'collaborator' %}
&nbsp; &nbsp; NPPS collaborator
{% endif %}
{% if include.short!='short' %}
  </td>
  <td>
{% endif %}

{% if person.tags contains 'leader' %}
&nbsp; &nbsp; Leadership team member
{% endif %}

{% if person.tags contains 'appointments' %}
&nbsp; &nbsp; {{ person.appointments }}
{% endif %}
  </td>
</tr>
