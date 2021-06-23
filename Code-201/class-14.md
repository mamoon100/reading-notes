# Part (a)

## CSS Transforms, Transitions, and Animations

### Transforms

With CSS3 came new ways to position and alter elements. Now general layout techniques can be revisited with alternative ways to size, position, and change elements. All of these new techniques are made possible by the transform property.

The transform property comes in two different settings, two-dimensional and three-dimensional. Each of these come with their own individual properties and values.

Within this lesson we’ll take a look at both two-dimensional and three-dimensional transforms. Generally speaking, browser support for the transform property isn’t great, but it is getting better every day. For the best support vendor prefixes are encouraged, however you may need to download the nightly version of Chrome to see all of these transforms in action.

The actual syntax for the transform property is quite simple, including the transform property followed by the value. The value specifies the transform type followed by a specific amount inside parentheses.

Transform Syntax
The actual syntax for the transform property is quite simple, including the transform property followed by the value. The value specifies the transform type followed by a specific amount inside parentheses.

```
div {
  -webkit-transform: scale(1.5);
     -moz-transform: scale(1.5);
       -o-transform: scale(1.5);
          transform: scale(1.5);
}
```

2D Transforms
Elements may be distorted, or transformed, on both a two-dimensional plane or a three-dimensional plane. Two-dimensional transforms work on the x and y axes, known as horizontal and vertical axes. Three-dimensional transforms work on both the x and y axes, as well as the z axis. These three-dimensional transforms help define not only the length and width of an element, but also the depth. We’ll start by discussing how to transform elements on a two-dimensional plane, and then work our way into three-dimensional transforms.

2D Rotate
The transform property accepts a handful of different values. The rotate value provides the ability to rotate an element from 0 to 360 degrees. Using a positive value will rotate an element clockwise, and using a negative value will rotate the element counterclockwise. The default point of rotation is the center of the element, 50% 50%, both horizontally and vertically. Later we will discuss how you can change this default point of rotation.

```
<figure class="box-1">Box 1</figure>
<figure class="box-2">Box 2</figure>
```

```
.box-1 {
  transform: rotate(20deg);
}
.box-2 {
  transform: rotate(-55deg);
}
```

2D Scale
Using the scale value within the transform property allows you to change the appeared size of an element. The default scale value is 1, therefore any value between .99 and .01 makes an element appear smaller while any value greater than or equal to 1.01 makes an element appear larger.

```
<figure class="box-1">Box 1</figure>
<figure class="box-2">Box 2</figure>
```

```
.box-1 {
  transform: scale(.75);
}
.box-2 {
  transform: scale(1.25);
}
```

2D Translate
The translate value works a bit like that of relative positioning, pushing and pulling an element in different directions without interrupting the normal flow of the document. Using the translateX value will change the position of an element on the horizontal axis while using the translateY value will change the position of an element on the vertical axis.

As with the scale value, to set both the x and y axis values at once, use the translate value and declare the x axis value first, followed by a comma, and then the y axis value.

The distance values used within the translate value may be any general length measurement, most commonly pixels or percentages. Positive values will push an element down and to the right of its default position while negative values will pull an element up and to the left of its default position.

```
<figure class="box-1">Box 1</figure>
<figure class="box-2">Box 2</figure>
<figure class="box-3">Box 3</figure>
```

```
.box-1 {
  transform: translateX(-10px);
}
.box-2 {
  transform: translateY(25%);
}
.box-3 {
  transform: translate(-10px, 25%);
}
```

2D Skew
The last transform value in the group, skew, is used to distort elements on the horizontal axis, vertical axis, or both. The syntax is very similar to that of the scale and translate values. Using the skewX value distorts an element on the horizontal axis while the skewY value distorts an element on the vertical axis. To distort an element on both axes the skew value is used, declaring the x axis value first, followed by a comma, and then the y axis value.%p

The distance calculation of the skew value is measured in units of degrees. Length measurements, such as pixels or percentages, do not apply here.

```
<figure class="box-1">Box 1</figure>
<figure class="box-2">Box 2</figure>
<figure class="box-3">Box 3</figure>
```

```
.box-1 {
  transform: skewX(5deg);
}
.box-2 {
  transform: skewY(-20deg);
}
.box-3 {
  transform: skew(5deg, -20deg);
}
```

### Transitions & Animations

One evolution with CSS3 was the ability to write behaviors for transitions and animations. Front end developers have been asking for the ability to design these interactions within HTML and CSS, without the use of JavaScript or Flash, for years. Now their wish has come true.

With CSS3 transitions you have the potential to alter the appearance and behavior of an element whenever a state change occurs, such as when it is hovered over, focused on, active, or targeted.

Animations within CSS3 allow the appearance and behavior of an element to be altered in multiple keyframes. Transitions provide a change from one state to another, while animations can set multiple points of transition upon different keyframes.

Transitions
As mentioned, for a transition to take place, an element must have a change in state, and different styles must be identified for each state. The easiest way for determining styles for different states is by using the :hover, :focus, :active, and :target pseudo-classes.

There are four transition related properties in total, including transition-property, transition-duration, transition-timing-function, and transition-delay. Not all of these are required to build a transition, with the first three are the most popular.

In the example below the box will change its background color over the course of 1 second in a linear fashion.

---------------------------------------------------------------

# part (b)

THE WORK ISSUE: REIMAGINING THE OFFICE

01. How to Build a Perfect Team
02. The War on Meetings
03. The Case for Blind Hiring
04. Failure to Lunch
05. The 'Good Jobs' Gamble
06. Rethinking the Work-Life Equation
07. The Rise of White-Collar Automation
08. The Post-Cubicle Office
09. The New Dream Jobs

Yet many of today’s most valuable firms have come to realize that analyzing and improving individual workers ­— a practice known as ‘‘employee performance optimization’’ — isn’t enough. As commerce becomes increasingly global and complex, the bulk of modern work is more and more team-based. One study, published in The Harvard Business Review last month, found that ‘‘the time spent by managers and employees in collaborative activities has ballooned by 50 percent or more’’ over the last two decades and that, at many companies, more than three-quarters of an employee’s day is spent communicating with colleagues.

In Silicon Valley, software engineers are encouraged to work together, in part because studies show that groups tend to innovate faster, see mistakes more quickly and find better solutions to problems. Studies also show that people working in teams tend to achieve better results and report higher job satisfaction. In a 2015 study, executives said that profitability increases when workers are persuaded to collaborate more. Within companies and conglomerates, as well as in government agencies and schools, teams are now the fundamental unit of organization. If a company wants to outstrip its competitors, it needs to influence not only how people work but also how they work together.

Five years ago, Google — one of the most public proselytizers of how studying workers can transform productivity — became focused on building the perfect team. In the last decade, the tech giant has spent untold millions of dollars measuring nearly every aspect of its employees’ lives. Google’s People Operations department has scrutinized everything from how frequently particular people eat together (the most productive employees tend to build larger networks by rotating dining companions) to which traits the best managers share (unsurprisingly, good communication and avoiding micromanaging is critical; more shocking, this was news to many Google managers).

The company’s top executives long believed that building the best teams meant combining the best people. They embraced other bits of conventional wisdom as well, like ‘‘It’s better to put introverts together,’’ said Abeer Dubey, a manager in Google’s People Analytics division, or ‘‘Teams are more effective when everyone is friends away from work.’’ But, Dubey went on, ‘‘it turned out no one had really studied which of those were true.’’

In 2012, the company embarked on an initiative — code-named Project Aristotle — to study hundreds of Google’s teams and figure out why some stumbled while others soared. Dubey, a leader of the project, gathered some of the company’s best statisticians, organizational psychologists, sociologists and engineers. He also needed researchers. Rozovsky, by then, had decided that what she wanted to do with her life was study people’s habits and tendencies. After graduating from Yale, she was hired by Google and was soon assigned to Project Aristotle.

project Aristotle’s researchers began by reviewing a half-century of academic studies looking at how teams worked. Were the best teams made up of people with similar interests? Or did it matter more whether everyone was motivated by the same kinds of rewards? Based on those studies, the researchers scrutinized the composition of groups inside Google: How often did teammates socialize outside the office? Did they have the same hobbies? Were their educational backgrounds similar? Was it better for all teammates to be outgoing or for all of them to be shy? They drew diagrams showing which teams had overlapping memberships and which groups had exceeded their departments’ goals. They studied how long teams stuck together and if gender balance seemed to have an impact on a team’s success.

No matter how researchers arranged the data, though, it was almost impossible to find patterns — or any evidence that the composition of a team made any difference. ‘‘We looked at 180 teams from all over the company,’’ Dubey said. ‘‘We had lots of data, but there was nothing showing that a mix of specific personality types or skills or backgrounds made any difference. The ‘who’ part of the equation didn’t seem to matter.’’

Some groups that were ranked among Google’s most effective teams, for instance, were composed of friends who socialized outside work. Others were made up of people who were basically strangers away from the conference room. Some groups sought strong managers. Others preferred a less hierarchical structure. Most confounding of all, two teams might have nearly identical makeups, with overlapping memberships, but radically different levels of effectiveness. ‘‘At Google, we’re good at finding patterns,’’ Dubey said. ‘‘There weren’t strong patterns here.’’

As they struggled to figure out what made a team successful, Rozovsky and her colleagues kept coming across research by psychologists and sociologists that focused on what are known as ‘‘group norms.’’ Norms are the traditions, behavioral standards and unwritten rules that govern how we function when we gather: One team may come to a consensus that avoiding disagreement is more valuable than debate; another team might develop a culture that encourages vigorous arguments and spurns groupthink. Norms can be unspoken or openly acknowledged, but their influence is often profound. Team members may behave in certain ways as individuals — they may chafe against authority or prefer working independently — but when they gather, the group’s norms typically override individual proclivities and encourage deference to the team.

Project Aristotle’s researchers began searching through the data they had collected, looking for norms. They looked for instances when team members described a particular behavior as an ‘‘unwritten rule’’ or when they explained certain things as part of the ‘‘team’s culture.’’ Some groups said that teammates interrupted one another constantly and that team leaders reinforced that behavior by interrupting others themselves. On other teams, leaders enforced conversational order, and when someone cut off a teammate, group members would politely ask everyone to wait his or her turn. Some teams celebrated birthdays and began each meeting with informal chitchat about weekend plans. Other groups got right to business and discouraged gossip. There were teams that contained outsize personalities who hewed to their group’s sedate norms, and others in which introverts came out of their shells as soon as meetings began.
