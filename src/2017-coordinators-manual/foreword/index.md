---
section_id: "000"
section_title: Foreword
acronymsOrdered:
  - NFIP
  - FEMA
  - CRS
  - FIRM
  - SFHA
---

The Community Rating System (CRS) is a national program developed by the Federal Emergency Management Agency (FEMA). The “Coordinator’s Manual” spells out the credits and credit criteria of the CRS for community activities and programs that go above and beyond the minimum requirements for participation in FEMA’s National Flood Insurance Program.

## Using the ”Coordinator’s Manual”

The “Coordinator’s Manual” is the guidebook for the Community Rating System. It explains how the
program operates, what is credited, and how credits are calculated. Although it is primarily a
reference for program. activities and credits, it can also help guide communities that want to design
or improve their floodplain management programs. This 2025 version of the “Coordinator’s
Manual” incorporates changes from the 2021 “Addendum to the 2017 CRS Coordinator’s Manual”
and the 2023 document, “A Supplement to CRS Credit.”

If you want to know how the Community Rating System works and how your community can benefit
from participating in the program and reduce flood insurance premiums,

- Start with Section 110 for an overview of the program.
- Section 200 describes the procedures for applying, required activities, calculating credits, and advancing in the program. Be sure to review the prerequisites for participation in Section 211.

If you want to develop a comprehensive community floodplain management program,

- Start with the Community Self-Assessment, Section 240, to help evaluate your existing flood problems, identify potential future flood problems, and to identify appropriate measures to address them.
- Use the results of the Community Self-Assessment to determine what additional data you need about your flood problem areas. Developing new data can be credited under Activity 410 (Flood Hazard Mapping).
- Review how to prepare a floodplain management plan, following the 10-step process described in Activity 510 (Floodplain Management Planning). If you have developed a multi-hazard mitigation plan, Activity 510 can still assist you in developing a more comprehensive plan for flood damage reduction.
- To develop an overall public information program, see the section on the Program for Public Information in Activity 330 (Outreach Projects).

If you want to improve a specific aspect of your existing floodplain management efforts, the CRS has 19 credited activities and additional sections and appendices that provide supplementary guidance and references. Here is a guide to what they cover.

- Assessing your community’s flood problem: Section 240
- Mapping and flood data
  - Developing new maps and data: Activity 410
  - Maintaining and providing maps and data: Activity 440 and Activity 320
  - Providing the data to people: Activity 320
  - Mapping special flood-related hazards (e.g., tsunamis, migrating stream channels, coastal erosion): Activity 320 and Activity 410.
- Managing new development to minimize future damage
  - Preserving open space: Activity 420
  - Protecting natural floodplain functions: Activity 420 and Activity 510
  - Regulating development in the floodplain: Activity 430 and Activity 310
  - Regulating development in the watershed: Activity 450
  - Managing special flood-related hazards (e.g., tsunamis, migrating stream channels, coastal erosion): Activity 420 and Activity 430.
- Developing a floodplain management plan for your community: Activity 510
  - Reducing flood losses to existing development
  - Acquiring or relocating flood-prone buildings out of harm’s way: Section 501, Activity 520, and Activity 530
  - Protecting flood-prone buildings in place: Activity 530
  - Improving your drainage system maintenance efforts: Activity 540
  - Addressing repetitively flooded properties: Activity 520 and Activity 530
- Improving emergency preparedness and response
  - Flood warning and response planning: Activity 610
  - Warning and response for areas protected by a levee: Activity 620
  - Warning and response for areas downstream of a dam: Activity 630
- Implementing public information activities
  - Developing a master public information program: Activity 330
  - Reaching out to people about floods and flood protection: Activity 330
  - Providing detailed information on the potential for flooding and protecting against flood damage: Activity 320, Activity 350, and Activity 360
  - Libraries: Activity 350
  - Websites: Activity 350
  - Disseminating information on flood insurance: Activity 370 and Activity 330
  - Assisting with real estate disclosure: Activity 340.

## More about the “Coordinator’s Manual”

This document uses some technical terms and acronyms. The terms are defined in the Glossary,
Section 120. The acronyms are listed in Appendix A. The most common acronyms are:

<dl class="acronyms">
  {%- assign sortedAcronyms = acronyms | where_exp: "i", "i.section == 'Foreword'" %}
  {%- assign ordered = "" | split: "" -%}
  {%- for key in acronymsOrdered -%}
    {%- assign match = sortedAcronyms | where: "term", key -%}
    {%- assign ordered = ordered | concat: match -%}
  {%- endfor -%}

{%- assign ordered = ordered -%}

{%- for entry in ordered -%}

<dt id="{{ entry.term | slugify }}">
<abbr title="{{ entry.definition | strip_html | strip_newlines | escape }}">
{{ entry.term }}
</abbr>
</dt>
<dd>{{ entry.definition }}</dd>
{% comment %} <dd>{{ entry.definition | md_first_inline }}</dd> {% endcomment %}
{%- endfor -%}

</dl>

Communities and other floodplain management professionals are encouraged to make suggestions
on both the content and the form of the CRS. Send them to fema-crs@fema.dhs.gov.

<nav aria-labelledby="toc-heading" class="my-4">
  <h2 id="toc-heading" class="visually-hidden">Manual contents</h2>

{%- assign topItems = contents
      | where: "type", "content"
      | where: "level", 0
      | reject: "title", "Appendices"
      | sort: "group" -%}

  <dl class="toc list-unstyled">

    {%- for top in topItems -%}
      <dt>
        <a href="{{ top.anchor }}">{{ top.title }}</a>
      </dt>

      {%- assign seconds = contents
          | where: "type", "content"
          | where: "group", top.group
          | where: "level", 1
          | sort: "id" -%}

      <dd>
        {%- if seconds and seconds.size > 0 -%}
          <ul class="list-unstyled ms-3" role="list">
            {%- for sec in seconds -%}
              <li>
                <a href="{{ sec.anchor }}">{{ sec.title }}</a>
              </li>
            {%- endfor -%}
          </ul>
        {%- endif -%}
      </dd>
    {%- endfor -%}

  </dl>
</nav>
