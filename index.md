---
layout: workshop      # DON'T CHANGE THIS.
root: .               # DON'T CHANGE THIS EITHER.  (THANK YOU.)
carpentry: "an"    # what kind of Carpentry (must be either "dc" or "swc")
venue: "ACENET Summer School 2023"   # brief name of host site without address (e.g., "Euphoric State University")
address: "Online"  # full street address of workshop (e.g., "Room A, 123 Forth Street, Blimingen, Euphoria")
country: "ca"      # lowercase two-letter ISO country code such as "fr" (see https://en.wikipedia.org/wiki/ISO_3166-1)
language: "en"     # lowercase two-letter ISO language code such as "fr" (see https://en.wikipedia.org/wiki/ISO_639-1)
latlng: "na/na"   # decimal latitude and longitude of workshop venue (e.g., "41.7901128,-87.6007318" - use http://www.latlong.net/)
humandate: "2023 May 16, 23, 30, June 6, 13"    # human-readable dates for the workshop (e.g., "Feb 17-18, 2020")
humantime: "9:30AM - 11:30AM, 1:00PM - 3:00PM ADT (UTC-3)"    # human-readable times for the workshop (e.g., "9:00 am - 4:30 pm")
startdate: 2023-05-16      # machine-readable start date for the workshop in YYYY-MM-DD format like 2015-01-01
enddate: 2023-06-13        # machine-readable end date for the workshop in YYYY-MM-DD format like 2015-01-02
instructor: ["Ross Dickson, Chris Geroux, Gurpreet Matharoo, Serguei Vassiliev, Oliver Stueker"] # boxed, comma-separated list of instructors' names as strings, like ["Kay McNulty", "Betty Jennings", "Betty Snyder"]
helper: ["(instructors)"]     # boxed, comma-separated list of helpers' names, like ["Marlyn Wescoff", "Fran Bilas", "Ruth Lichterman"]
contact: ["ross.dickson@ace-net.ca"]    # boxed, comma-separated list of contact email addresses for the host, lead instructor, or whoever else is handling questions, like ["marlyn.wescoff@example.org", "fran.bilas@example.org", "ruth.lichterman@example.org"]
etherpad:    # optional: URL for the workshop Etherpad if there is one
eventbrite:  # optional: alphanumeric key for Eventbrite registration, e.g., "1234567890AB" (if Eventbrite is being used)
---

{% if page.eventbrite %}
<iframe
  src="https://www.eventbrite.ca/tickets-external?eid={{page.eventbrite}}&ref=etckt"
  frameborder="0"
  width="100%"
  height="375px"
  scrolling="auto">
</iframe>
{% endif %}

<h4>This site contains the general information for the 2023 Summer School in Advanced Research Computing, put on by ACENET.</h4>

<h2 id="general">General Information</h2>

<!--
  INTRODUCTION

  Edit the general explanatory paragraph below if you want to change
  the pitch.
-->
<p>
The ACENET Summer School in Advanced Research Computing seeks to educate 
researchers in those tools and techniques used in high-performance computing
and scientific computation. Topics will include general parallel computing,
OpenMP, GPGPU, and MPI programming, and machine learning.  
</p>

<!--
  AUDIENCE

  Explain who your audience is.  (In particular, tell readers if the
  workshop is only open to people from a particular institution.
-->
<p id="who">
  <strong>Who:</strong>
  The course is aimed at researchers, both academic and industrial. 
  The background expected is typically that of a graduate student, 
  although both advanced undergraduates and those who have finished (or never been to) graduate school may expect to benefit.
  Participants attending the school must have familiarity with the Unix command line, and some level of programming experience. 
  Participating in the ACENET Basics Series would be a great foundation for the school.
</p>

<!--
  LOCATION

  This block displays the address and links to maps showing directions
  if the latitude and longitude of the workshop have been set.  You
  can use http://itouchmap.com/latlong.html to find the lat/long of an
  address.

{% if page.latlng %}
<p id="where">
  <strong>Where:</strong>
  {{page.address}}.
  Get directions with
  <a href="//www.openstreetmap.org/?mlat={{page.latlng | replace:',','&mlon='}}&zoom=16">OpenStreetMap</a>
  or
  <a href="//maps.google.com/maps?q={{page.latlng}}">Google Maps</a>.
</p>
{% endif %}
-->
<!--
  SPECIAL REQUIREMENTS

  Modify the block below if there are any special requirements.
-->
<p id="requirements">
  <strong>Requirements:</strong> 
  This course will be delivered on-line.
  <ul>
  <li>You must have a computer and internet service of sufficient quality to
      participate in a Zoom videoconference.  We recommend a headset.</li>
  <li>You may also find a second monitor useful if you can obtain one.</li>
  <li>For software requirements, see "Setup" below.</li>
  <li>You will be expected to abide by Software Carpentry's
    <a href="{{site.swc_site}}/conduct.html">Code of Conduct</a>.</li>
  </ul>
</p>
  
<h2 id="setup">Setup</h2>

  <h3>Zoom</h3>
  <p>
    This online training will be conducted using Zoom video conferencing. 
    Please download and install <a href="https://zoom.us/download">Zoom Client for Meetings</a>.
  </p>

<h3>SSH client</h3>
<p>
  You must have an <a href="https://docs.alliancecan.ca/wiki/SSH">SSH client</a> installed on your computer, 
  and be able to connect to an Alliance cluster with it.
</p>

<!--
  ACCESSIBILITY

  Modify the block below if there are any barriers to accessibility or
  special instructions.
-->
<!--
//<p id="accessibility">
//  <strong>Accessibility:</strong> We are committed to making this workshop
//  accessible to everybody.
//  The workshop organisers have checked that:
//</p>
//<ul>
//  <li>The room is wheelchair / scooter accessible.</li>
//  <li>Accessible restrooms are available.</li>
//</ul>
//<p>
//  Materials will be provided in advance of the workshop and
//  large-print handouts are available if needed by notifying the
//  organizers in advance.  If we can help making learning easier for
//  you (e.g. sign-language interpreters, lactation facilities) please
//  <a href="mailto:{{page.contact}}">get in touch</a> and we will
//  attempt to provide them.
//</p>
-->
<!--
  CONTACT EMAIL ADDRESS

  Display the contact email address set in the configuration file.
-->
<p id="contact">
  <strong>Contact</strong>:
  Please email
  {% if page.contact %}
    {% for contact in page.contact %}
      {% if forloop.last and page.contact.size > 1 %}
        or
      {% else %}
        {% unless forloop.first %}
        ,
        {% endunless %}
      {% endif %}
      <a href='mailto:{{contact}}'>{{contact}}</a>
    {% endfor %}
  {% else %}
    to-be-announced
  {% endif %}
  for more information.
</p>

<hr/>

<!--
  SCHEDULE

  Show the workshop's schedule.  Edit the items and times in the table
  to match your plans.  You may also want to change 'Day 1' and 'Day
  2' to be actual dates or days of the week.
-->
<h2 id="schedule">Schedule</h2>

<div class="row">
  <div class="col-md-6">
    <h3> Tuesday, May 16</h3>
    <table class="table table-striped">
      <tr> <td> 09:30-11:30, 13:00-15:00 Atlantic</td> <td> <a href="https://acenet-arc.github.io/ACENET_Summer_School_General/">General Overview</a> </td></tr>
      <tr> <td> </td> <td>Ross/Serguei?</td> </tr>
    </table>
  </div>
  <div class="col-md-6">
    <h3> Tuesday, May 23</h3>
    <table class="table table-striped">
      <tr> <td> 09:30-11:30,  13:00-15:00 Atlantic</td> <td> <a href="https://acenet-arc.github.io/ACENET_Summer_School_Dask/">Dask</a> </td></tr>
      <tr> <td> </td> <td> C. Geroux </td> </tr>
    </table>
  </div>
  <div class="col-md-6">
    <h3> Tuesday, May 30</h3>
    <table class="table table-striped">
      <tr> <td> 09:30-11:30, 13:00-15:00 Atlantic</td> <td> <a href="https://acenet-arc.github.io/ACENET_Summer_School_OpenMP_ACC/">Open MP</a> </td></tr>
      <tr> <td> </td> <td> S. Vassiliev</td> </tr>
    </table>
  </div>
  <div class="col-md-6">
    <h3> Tuesday, June 6</h3>
    <table class="table table-striped">
      <tr> <td> 09:30-11:30, 13:00-15:00 Atlantic</td> <td><a href="https://acenet-arc.github.io/ACENET_Summer_School_MPI/">MPI Programming</a></td></tr>
      <tr> <td> </td> <td> G. Matharoo </td> </tr>
    </table>
  </div>
  <div class="col-md-6">
    <h3> Tuesday, June 13</h3>
    <table class="table table-striped">
      <tr> <td> 09:30-11:30 Atlantic</td> <td> <a href="https://acenet-arc.github.io/ACENET_Summer_School_GPGPU/">GPU Programming with CUDA</a> </td></tr>
      <tr> <td> </td> <td> R. Dickson</td> </tr>
      <tr> <td> 13:00-15:00 Atlantic</td> <td> <a href="https://docs.alliancecan.ca/wiki/OpenACC_Tutorial">GPU Programming with OpenACC</a> </td></tr>
      <tr> <td> </td> <td> O. Stueker</td> </tr>
    </table>
  </div>

  <h3 id="OfficeHours">Office hours</h3>
  <p>Instructional staff will be available in the Zoom room 
    between the hours of 11:00 AM and noon (Atlantic time) each Friday 
    to answer questions or provide help with exercises or technical issues related to the School.
  </p>
  <p>You may also contact the instructors and request to schedule a meeting at any other time,
    subject to the instructor's availability.
  </p>

<!--
  ETHERPAD

  At `_misc/etherpad.txt` you will find a template for the etherpad.

  Display the Etherpad for the workshop.  You can set this up in
  advance or on the first day; either way, make sure you push changes
  to GitHub after you have its URL.  To create an Etherpad, go to

      http://pad.software-carpentry.org/YYYY-MM-DD-site

  where 'YYYY-MM-DD-site' is the identifier for your workshop,
  e.g., '2015-06-10-esu'.
-->
{% if page.etherpad %}
<p id="etherpad">
  <strong>Etherpad:</strong> <a href="{{page.etherpad}}">{{page.etherpad}}</a>.
  <br/>
  We will use this Etherpad for chatting, taking notes, and sharing URLs and bits of code.
</p>
{% endif %}

<hr/>

<!--
  SYLLABUS

  Show what topics will be covered.

  1. If your workshop is R rather than Python, remove the comment
     around that section and put a comment around the Python section.
  2. Some workshops will delete SQL.
  3. Please make sure the list of topics is synchronized with what you
     intend to teach.
  4. You may need to move the div's with class="col-md-6" around inside
     the div's with class="row" to balance the multi-column layout.

  This is one of the places where people frequently make mistakes, so
  please preview your site before committing, and make sure to run
  'tools/check' as well.
-->
<h2 id="syllabus">Syllabus</h2>

<div class="row">
  
  <div class="col-md-6">
    <h3 id="syllabus-parallel"><a href="https://ssvassiliev.github.io/Summer_School_General/">General parallel computing and working at scale</a></h3>
    <ul>
      <li>performance measurement, and factors affecting performance</li>
      <li>I/O and data movement</li>
      <li>schedulers and “embarrassingly parallel” jobs</li>
      <li>analyzing performance using a profiler</li>
      <!-- <li>MapReduce, Spark, Hadoop, and all that</li> -->
      <li><a href="{{site.repo_pages}}/ACENET_Summer_School_General/reference/">Reference...</a></li>
    </ul>
  </div>
  <div class="col-md-6">
    <h3 id="syllabus-dask"><a href="{{site.repo_pages}}/ACENET_Summer_School_Dask/">Dask: parallel computing with python</a></h3>
    <ul>
      <li><a href="{{site.repo_pages}}/ACENET_Summer_School_Dask/reference/">Reference...</a></li>
    </ul>
  </div>
  
</div>

<div class="row">
  
  
  <div class="col-md-6">
    <h3 id="syllabus-openmp"><a href="https://ssvassiliev.github.io/Summer_School_OpenMP/">OpenMP, shared memory, and threads</a></h3>
    <ul>
      <li>OpenMP</li>
      <li>Shared memory</li>
      <li>Threads</li>
      <li><a href="{{site.repo_pages}}/ACENET_Summer_School_OpenMP/reference/">Reference...</a></li>
    </ul>
  </div>
  <!--
  <div class="col-md-6">
    <h3 id="syllabus-ml"><a href="https://github.com/calculquebec/intro-machine-learning">Machine Learning (ML)</a></h3>
    <ul>
      <li>Fundamentals of machine learning, what it is and how it works "under the hood"</li>
      <li>Use scikit-learn and Python to demonstrate how ML works in practice</li>
      <li>Neural networks illustrated using PyTorch</li>
      <li>Scale up a neural network by streamlining the workflow</li>
      <li>Use GPUs for neural network training</li>
    </ul>
  </div>
  -->
  
  <div class="col-md-6">
    <h3 id="syllabus-mpi"><a href="https://acenet-arc.github.io/ACENET_Summer_School_MPI/">Message Passing Interface (MPI)</a></h3>
    <ul>
      <li>MPI</li>
      <li><a href="{{site.repo_pages}}/ACENET_Summer_School_MPI/reference/">Reference...</a></li>
    </ul>
  </div>

  
</div>

<div class="row">
  
  <div class="col-md-6">
    <h3 id="syllabus-gpgpu"><a href="https://acenet-arc.github.io/ACENET_Summer_School_GPGPU/">GPGPU</a></h3>
    <ul>
      <li>CUDA</li>
      <li><a href="{{site.repo_pages}}/ACENET_Summer_School_GPGPU/reference/">Reference...</a></li>
    </ul>
  </div>
  
</div>

<hr/>

<!--
  SETUP

  Delete irrelevant sections from the setup instructions.  Each
  section is inside a 'div' without any classes to make the beginning
  and end easier to find.

  This is the other place where people frequently make mistakes, so
  please preview your site before committing, and make sure to run
  'tools/check' as well.
-->
