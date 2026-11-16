---
title: "CMU 17-444: Production Machine Learning Systems for Software Engineers"
hide:
  - navigation
---

# 17-444 Production Machine Learning Systems for Software Engineers

**From Prototype to Production.** *You can build an AI demo. Can you build a system people can depend on?* See the [course overview](overview.md).

!!! info "Spring 2027 · Under construction"
    The course is still being planned. The schedule below is tentative, and the syllabus, assignments, and readings will be posted as they are finalized.

## This Week


<div id="this-week">


{%- set this_week = extra.this_week -%}

<div class="card">
    <div class="header">
        Lectures & Readings
    </div>
    <div class="content">
        {% if this_week.lectures %}
            {% for lecture in this_week.lectures %}
                <div class="lecture-name">
                    {{ lecture.name }}
                </div>
                <div class="lecture-date">
                    <span class="material-symbols-outlined">calendar_month</span>
                    {{ lecture.date }}
                </div>

                {% if lecture.link != "" %}
                <a class="label label-gold" href="{{lecture.link}}" target="_blank">
                    <span class="material-symbols-outlined">slideshow</span>
                    Slides
                </a>
                {% endif %}

                {% if lecture.reading %}
                    <a class="label label-blue" href="{{lecture.reading.link}}" target="_blank">
                        <span class="material-symbols-outlined">link</span>
                        {{lecture.reading.name}}
                    </a>
                {% endif %}
                {% if not loop.last %}
                <hr/>
                {% endif %}
            {% endfor %}
        {% else %}
            None!
        {% endif %}
    </div>

</div>

<div class="card">
    <div class="header">
        Lab
    </div>
    <div class="content">
        {% if this_week.lab %}
            <div class="recitation-name">
                {{ this_week.lab.name }}
            </div>
            <div class="lecture-date">
                <span class="material-symbols-outlined">calendar_month</span>
                {{ this_week.lab.date }}
            </div>

            {% if this_week.lab.slides != "" %}
            <a class="label label-aqua" href="{{this_week.lab.slides}}" target="_blank">
                <span class="material-symbols-outlined">slideshow</span>Slides
            </a>
            {% endif %}

            {% if this_week.lab.handout != "" %}
            <a class="label label-aqua" href="{{this_week.lab.handout}}">
                <span class="material-symbols-outlined">description</span>Handout
            </a>
            {% endif %}
        {% else %}
            None!
        {% endif %}
    </div>

    <div class="header">
        Office Hours
    </div>
    <div class="content">
        By appointment. See <a href="#staff">staff</a> below.
    </div>

</div>

<div class="card">
    <div class="header">
        Assignments & Project
    </div>
    <div class="content">
        {% if this_week.projects %}
            {% for project in this_week.projects %}
                <div class="homework-name">
                    {{ project.name }}
                </div>

                <div class="homework-date">
                    <span class="material-symbols-outlined">calendar_month</span>
                    Released {{ project.date }}
                </div>

                {% if project.deadline != "" %}
                <div class="homework-date">
                    <span class="material-symbols-outlined">calendar_month</span>
                    {{ project.deadline }}
                </div>
                {% endif %}

                {% if project.link != "" %}
                <a class="label label-red" href="{{project.link}}">
                    <span class="material-symbols-outlined">description</span>Handout
                </a>
                {% endif %}
                {% if not loop.last %}
                <hr/>
                {% endif %}
            {% endfor %}
        {% else %}
            None!
        {% endif %}
    </div>
    <div class="header">
        Team Survey
    </div>
    <div class="content">
        {% if this_week.teamsurvey %}
            <div class="recitation-name">
                {{ this_week.teamsurvey.name }}
            </div>

            {% if this_week.teamsurvey.link != "" %}
            <a class="label label-aqua" href="{{this_week.teamsurvey.link}}" target="_blank">
                <span class="material-symbols-outlined">equalizer</span>Survey
            </a>
	    {% else %}
	    Not opened yet! Opens on {{ this_week.teamsurvey.opendate }}.
            {% endif %}
        {% else %}
            None!
        {% endif %}
    </div>


</div>

<div class="card">
    <div class="header">
        Problem Sets & Quizzes
    </div>
    <div class="content">
        {% if this_week.problemsets %}
            {% for problemset in this_week.problemsets %}
                <div class="homework-name">
                    {{ problemset.name }}
                </div>

                <div class="homework-date">
                    <span class="material-symbols-outlined">calendar_month</span>
                    Released {{ problemset.date }}
                </div>

                {% if problemset.deadline != "" %}
                <div class="homework-date">
                    <span class="material-symbols-outlined">calendar_month</span>
                    {{ problemset.deadline }}
                </div>
                {% endif %}

                {% if problemset.link != "" %}
                <a class="label label-red" href="{{problemset.link}}">
                    <span class="material-symbols-outlined">description</span>Handout
                </a>
                {% endif %}
                {% if not loop.last %}
                <hr/>
                {% endif %}
            {% endfor %}
        {% else %}
            None!
        {% endif %}
    </div>
</div>

</div>

## Weekly Schedule (Tentative)

<div id="schedule" markdown>

<!-- Loading in schedule from schedule.yaml -->

{%- set schedule = extra.schedule -%}

{% if schedule %}
{% set ns = namespace(homework_days_left=0, problemset_days_left=0) %}

<table>
    <thead>
        <th><b>Date</b></th>
        <th><b>Lecture</b></th>
        <th><b>Pre-lecture Reading</b></th>
        <th><b>Lab</b></th>
        <th><b>Problem Sets / Quiz</b></th>
        <th><b>Assignments & Project</b></th>
    </thead>
    <tbody>
        {% for schedule_day in schedule %}
        <tr>
            <td><span class="schedule-day">{{schedule_day.date}}</span></td>

            <td><span class="schedule-lecture">
                {% if schedule_day.lecture.name != "" and schedule_day.lecture.link != "" %}
                    <a class="label label-gold" href="{{schedule_day.lecture.link}}" target="_blank">
                        {{schedule_day.lecture.name}}
                    </a>
                {% elif schedule_day.lecture.name != "" %}
                    <b>{{schedule_day.lecture.name}}</b>
                {% endif %}
            </span></td>

            <td><span class="schedule-reading">
                {% if schedule_day.reading.name != "" %}
                    <a class="label label-blue" href="{{schedule_day.reading.link}}" target="_blank">
                        {{schedule_day.reading.name}}
                    </a>
                {% endif %}
            </span></td>

            <td><span class="schedule-recitation">
                {% if schedule_day.lab.name != "" %}
                    <b>{{schedule_day.lab.name}}</b>
                    <br/>

                    {% if schedule_day.lab.slides != "" %}
                    <a class="label label-aqua" href="{{schedule_day.lab.slides}}" target="_blank">
                        <span class="material-symbols-outlined">slideshow</span>Slides
                    </a>
                    {% endif %}

                    {% if schedule_day.lab.handout != "" %}
                    <a class="label label-aqua" href="{{schedule_day.lab.handout}}">
                        <span class="material-symbols-outlined">description</span>Handout
                    </a>
                    {% endif %}
                {% endif %}
            </span></td>


            {% if schedule_day.problemset.name != "" %}
                <td rowspan="{{schedule_day.problemset.numDays}}"><span class="schedule-problemset">
                    <b>{{schedule_day.problemset.name}}</b>
                    <br/>
                    {{schedule_day.problemset.deadline}}
                    <br/>

                    {% if schedule_day.problemset.link != "" %}
                    <a class="label label-gold" href="{{schedule_day.problemset.link}}">
                        <span class="material-symbols-outlined">description</span>Handout
                    </a>
                    {% endif %}
                </span></td>
                {% set ns.problemset_days_left = schedule_day.problemset.numDays - 1 %}
            {% else %}
                {% if ns.problemset_days_left > 0 %}
                    {% set ns.problemset_days_left = ns.problemset_days_left - 1 %}
                {% else %}
                    <td><span class="schedule-problemset"></span></td>
                {% endif %}
            {% endif %}

            {%- set has_assignment = schedule_day.assignment and schedule_day.assignment.name != "" -%}
            {% if schedule_day.homework.name != "" or has_assignment %}
                <td rowspan="{{ schedule_day.homework.numDays if schedule_day.homework.name != '' else 1 }}"><span class="schedule-homework">
                    {% for item in [schedule_day.assignment, schedule_day.homework] if item and item.name != "" %}
                    <b>{{item.name}}</b>
                    <br/>
                    {% if item.deadline != "" %}
                    {{item.deadline}}
                    <br/>
                    {% endif %}

                    {% if item.link != "" %}
                    <a class="label label-red" href="{{item.link}}" target="_blank">
                        <span class="material-symbols-outlined">description</span>Handout
                    </a>
                    {% endif %}
                    {% if not loop.last %}<br/><br/>{% endif %}
                    {% endfor %}
                </span></td>
                {% set ns.homework_days_left = (schedule_day.homework.numDays if schedule_day.homework.name != '' else 1) - 1 %}
            {% else %}
                {% if ns.homework_days_left > 0 %}
                    {% set ns.homework_days_left = ns.homework_days_left - 1 %}
                {% else %}
                    <td><span class="schedule-homework"></span></td>
                {% endif %}
            {% endif %}
        </tr>
        {% endfor %}
    </tbody>

</table>

{% else %}
Coming Soon!
{% endif %}

</div>

## Staff

### Instructor

<div id="course-instructors">
{%- set instructors = extra.staff | selectattr("role", "==", "Instructor") | list -%}
{% for instructor in instructors %}
<div class="staffer card">
    <div class="container">
        <img class="staffer-image" src="assets/images/{{instructor.photo}}" alt="">
        <div>
            <h3 class="staffer-name">
                {{instructor.name}}
            </h3>
            <div class="staffer-links">
                <a href="mailto:{{instructor.email}}"><span class="material-symbols-outlined">
                    mail
                </span></a><br />
		Office hours <a href="https://calendar.app.google/BcUUbyXDAzcw8xCZ7" style=""> by appointment </a><br />
                {% if instructor.website %}
                <a href="{{instructor.website}}" target="_blank"><span class="material-symbols-outlined">
                    public
                </span></a>
                {% endif %}
            </div>
        </div>
    </div>
</div>
{% endfor %}

</div>

{%- set assistants = extra.staff | selectattr("role", "==", "Teaching Assistant") | list -%}
{%- set num_teaching_assistants = assistants | count -%}

{% if num_teaching_assistants > 0 %}

### Teaching Assistant

<div id="course-assistants">

{% for assistant in assistants %}

<div class="staffer card">
    <div class="container">
        <img class="staffer-image" src="assets/images/{{assistant.photo}}" alt="">
        <div>
            <h3 class="staffer-name">
                {{assistant.name}}
            </h3>
            <div class="staffer-links">
                <a href="mailto:{{assistant.email}}"><span class="material-symbols-outlined">
                    mail
                </span></a>
                Office hours <a href="https://calendar.app.google/zdagEejde357hGa1A" style="font-size: inherit; color: #f45b5b;">by appointment</a><br />
                {% if assistant.website %}
                <a href="{{assistant.website}}" target="_blank"><span class="material-symbols-outlined">
                    public
                </span></a>
                {% endif %}
            </div>
        </div>
    </div>
</div>
{% endfor %}

</div>
{% endif %}

{%- set assistants = extra.staff | selectattr("role", "==", "Course Assistant") | list -%}
{%- set num_teaching_assistants = assistants | count -%}

{% if num_teaching_assistants > 0 %}

### Course Assistants

<div id="course-assistants">

{% for assistant in assistants %}

<div class="staffer card">
    <div class="container">
        <img class="staffer-image" src="assets/images/{{assistant.photo}}" alt="">
        <div>
            <h3 class="staffer-name">
                {{assistant.name}}
            </h3>
            <div class="staffer-links">
                <a href="mailto:{{assistant.email}}"><span class="material-symbols-outlined">
                    mail
                </span></a>
                {% if assistant.website %}
                <a href="{{assistant.website}}" target="_blank"><span class="material-symbols-outlined">
                    public
                </span></a>
                {% endif %}
            </div>
        </div>
    </div>
</div>
{% endfor %}

</div>
{% endif %}
