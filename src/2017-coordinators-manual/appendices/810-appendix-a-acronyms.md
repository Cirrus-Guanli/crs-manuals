---
section_id: "810"
section_title: Appendix A. Acronyms
---

The acronyms used in the “Coordinator’s Manual” are listed below. The section number tells where the first detailed description of the acronym appears.

Most of the acronyms are elements of the credited activities in the 300 through 600 series. All elements are in capital letters. Attributes of an element are in lower-case letters. The lower-case letters, “a,” “b,” “c,” and “r,” are prefixes. The letters “i,” “n,” and “s” are suffixes to the elements. For example, “bAR” represents the number of buildings acquired or relocated. The “b” is described in Section 302 and the “AR” is described in Section 522.

<table class="table table-striped table--acronyms">
  <caption class="visually-hidden">
    Acronyms used in the “Coordinator’s Manual”
  </caption>
  <thead>
    <th scope="col">Acronym</th>
    <th scope="col">Section</th>
    <th scope="col">Description</th>
  </thead>
  <tbody>
    {% assign sortedAcronyms = acronyms | sort_natural: "term" %}
    {%- for entry in sortedAcronyms %}
      <tr id="{{ entry.term | slugify }}">
        <th scope="row">
          <abbr title="{{ entry.definition | strip_html | strip_newlines | escape }}">
            {{ entry.term }}
          </abbr>
        </th>
        <td>{{ entry.section }}</td>
        <td>{{ entry.definition }}</td>
      </tr>
    {% endfor -%}
  </tbody>
</table>
