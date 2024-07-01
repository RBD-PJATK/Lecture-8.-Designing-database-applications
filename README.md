# Lecture 8. Designing database applications

<h3>Abstract</h3>

<p>To design and to implement an information system is never an easy task.
This is why engineers codified the general rules which drive the development.
For example, some of these rules apply to the management of the project team. 
In order to pass the subject <i>Relational databases</i>, a student must
do a project. During this lecture, we will define several simple rules
for these projects.</p>

<p>In the second part of this lecture we present the sketch of a slightly more complex
and complete methodology of software development. Its name is <i>MSF</i>
(= <i>Microsoft Solutions Framework</i>).</p>

<p>The development of information systems will be considered in more
detail during the lectures: <i>Design of information systems</i> and
<i>Construction and integration of information systems</i>.  This problem
will be discussed in the object-oriented design environment.</p> 

<hr><h3><a name="Projektowanie">Development of an application</a></h3>

<p>A file created by MS Access contains a set of objects: tables, queries,
forms, reports, pages, macros and modules. If these objects are integrated into one
coherent whole, this file is <i>an application</i>.  The user of an application
can focus on business functions and he/she does not have to manipulate objects in the
standard interface of MS Access.</p>

<p>The objects of an application:</p>

<ul>
<li>have properties which can be set appropriately, so that the objects look and work
	as required. For example, the property <i>Allow Edits</i> of a form
	decides whether a user can edit rows by means of this form.
<li>They automatically respond to events. For example, when a user changes the value
	of a text box, the system automatically checks if this value is of the proper type.
	The events are handled in forms, reports and controls.
<li>The response to an event may be predefined (the system performs some built-in action) or
	customized by the programmer (written as a procedure to be run in case of
	the event).
</ul>


<hr><h3><a name="Etapy">Phases of development of a database application</a></h3>

<p>Most methodologies of software development include the following phases.</p>

<ol>
<li><i>Strategy</i> (<i>initial analysis of the problem</i>)
<li><i>Detailed analysis of the problem</i>
<li><i>Design of the system</i>
<li><i>Implementation of the system</i> (with development of documentation and testing)
<li><i>Deployment of the system</i>
</ol>

<hr><h3><a name="Analiza">Analysis</a></h3>

<p><i>The analysis</i> (initial and detailed) should state the purpose and the scope
of the application.</p>

<ul>
<li>As a result of interviews with future users, analysts develop
	the list of tasks to be carried out by the application.
<li>Analysts examine copies of paper forms and reports which are currently used.
<li>Analysts identify the data that is processed and the relationships inside it
	(they draw an entity-relationship diagram).
</ul>

<hr><h3><a name="Proj">Design, prototyping and implementation</a></h3>

<p>The result of the <i>design, prototyping and implementation</i> stage
is the set of objects (tables, queries, forms, reports, pages and modules)
of the application.</p>

<p>The design may be conducted according to one of the two methods: <i>bottom-up</i> and
<i>top-down</i>.</p>

<h4>Top-down</h4>

<ol>
<li>Design the tables and their relationships.
<li>By means of a CASE tool generate the database schema from the entity-relationship diagram.
<li>Design the structure of the application as a tree (or a general graph). 
<li>When the graph is ready, generate (or develop) an initial prototype of the application
	which
	illustrates the control structure and the user interface of the application.
<li>Present the prototype to the users, so that they can check the chosen design. The prototype must not
	be used as the final application.  It is to be thrown out. 
</ol>


<p align="center"><img border="0" src="https://gakko.pjwstk.edu.pl/materialy/2398/lec/wyklad08/images/8_1.png"></p>

<p><b>Vertexes</b> of the structure of the application are forms, reports, pages and procedures.
They may have properties like <i>the type of a form</i>, which is 
one of: <i>control panel</i>, <i>informative</i>, <i>data entry</i>, <i>data display</i>,
	<i>data maintenance</i>, <i>filter</i>. There exists a similar classification for reports.</p>

<p>Each kind of processing operation (entry, update, search) should be associated with a separate form. Similar forms may
be unified later for the sake of the convenience of the user and the efficiency.</p>

<p><b>Edges</b> (arrows) of the structure of the application represent paths between the vertexes (e.g. forms).</p>

<p><b>The root</b> is a selected vertex. 
It is the form that is displayed when the user logs into the system.</p>

<h4>Bottom-up</h4>

<ol>
<li>Prepare the database as in the previous methods.
<li>Design forms and reports.  Add select queries if they are necessary.
<li>Create queries and procedures which are necessary to run the form or report.
<li>Test the forms and reports. Make sure that they allow performing any necessary operation.
<li>Integrate the forms and reports by appropriate paths among them.  Use buttons on forms, customized menus
	and event procedures.
</ol>

<hr><h3> <a name="Dokumentacja">Project documentation</a></h3>

<p><i>The project documentation</i> must be developed and maintained 
during the whole project.  It is a report on the results achieved by the project team.
It is a very important component of the project effort.</p>

<ul>
<li>The project documentation is crucial to the approval of the results of a development phase.
<li>It is used to plan the next phase.
<li>It is a means of communication among stakeholders of the project:
	customers, users, analysts, designers, programmers etc.
<li>It helps to harness the complexity and to codify the knowledge on the application.
<li>It connects the users' needs with the application and its limitations.
<li>It is necessary for system maintenance during its operation.
</ul>

<p>Usually the project documentation is stored in the database of a CASE tool. This database
is called <i>the repository</i>.</p>

<h4><a name="Fazy_strat">Documents of the strategy phase</a></h4>

<p>At the beginning of the project you create the document which states the needs, tasks and limits.
It is called the <a name="TOR"><i>TOR</i> (= <i>Terms Of Reference</i>)</a>.  Here is the list of its parts:

<dl>

<dt><b>Project name</b>
<dd>The name of the project.

<dt><b>Context</b>
<dd>A description of the environment, where it is planned to develop the application.

<dt><b>Needs</b>
<dd>The explanation why this database application is needed, etc. It contains also
	the reasoning which shows that expected profits exceed the expected costs.
	
<dt><b>Scope and limits</b>
<dd>What functions are in (to be implemented) and what functions are out. What are the limits
	of
	the budget, the staff and the schedule. What are the expected obstacles?
</dl>

<h4><a name="Fazy_analizy">Documents of the analysis phase</a></h4>

<ol>
<li>The entity-relationship model, i.e. entity-relationship diagrams and descriptions of all entities, attributes and relationships.
<li>The collection of business functions with information how to implement them in the database application.
<li>The list of system user groups and for each business functions the list of functions
	which will be used by this group.
</ol>

<h4><a name="Fazy_proj">Documents of the design phase</a></h4>

<ol>
<li>The design schema of the database (tables, columns, primary keys, foreign keys, views, indexes).
<li>The list of modules of the system (forms, reports etc.) together with the descriptions of the associations among them.
	Should be supplemented by diagrams showing modules and their connections. 
</ol>

<h4>Documents of the implementation phase</h4>

<ol>
<li>Operational application.
<li>Documentation for end users (e.g. the user manual).
<li>Documentation for system administrators.
<li>Technical documentation for those who will maintain and modify the system.
</ol>

<h4>Other phases</h4>

<p><i>The deployment phase</i> includes installation of the system, user training and data entry
	(it can also be the migration of the data from the previous system).</p>

<p>During <i>the operation phase</i> many changes are made in the system.  The presence of good
documentation facilitates the introduction of changes.  Each change should cause appropriate
update of the documentation.</p>

<p>Each phase of a project transforms information gathered during the previous phase. </p>

<ul>
<li>The general specification of data is transformed into the entity-relationship
	model, which
	then gets developed into the schema of the database and eventually becomes the database.
<li>The general specification of functions is formalized as the list of functions that then is
	transformed into diagrams and definitions of modules. These definitions are the basis
	to develop the application and its documentation (both user and technical).
</ul>

<h4>Prototyping</h4>

<p>Prototyping is a useful technique in software development.
<i>A prototype</i> is a trial application which can be developed much before the implementation begins.
If we can observe the operation of the prototypes, we can make sure that we have properly understood the user
requirements on the data presentation, business functions and the graphical interface of the application.</p>

<hr><h3><a name="CASE">CASE</a></h3>

<p>Software development may be supported by <i>CASE</i> tools (= <i>Computer-Aided Software Engineering</i>).
Such tools can automate some project activities.</p>

<ol>
<li>A CASE tool is focused on computer-based support for the 
	analysis and design phases.  It also facilitates
	using the results of these phases in the implementation phase.
<li>A CASE tool runs <i><a name="repozytorium">the repository</a></i>, i.e. the database
	which stores 
	all design objects (also documents) ever developed
	and used by the whole project team.  The repository contains:
	<ul>
	<li>diagrams, e.g. entity-relationship diagrams,
	<li>elements of diagrams, e.g. entities, functions, processes, modules, tables.
	<li>design representations of physical database objects, e.g. indexes, tablespaces, rollback segments.
	<li>documents, e.g. business terminology, goals, critical success factors.
	</ul>

<li>The repository is divided into parts called <i>applications systems</i> or <i>folders</i>.
<li>The objects gathered in the repository can be:
	<dl>
	<dt><i>transformed</i>,
	<dd>An object of the earlier phase gets transformed into 
	the object of the later phase, e.g. en entity is transformed into a table.
	<dt><i>versioned</i>,
	<dd>The repository maintains and labels all versions of the object.
	<dt><i>forward engineered</i>,
	<dd>The CASE tool automatically generates applications objects (tables, forms) from the repository objects (entities, modules).
	<dt><i>reverse engineered</i>,
	<dd>The CASE tool automatically generates repository objects (entities, modules) from the repository objects (tables, forms).
	<dt><i>shared</i>.
	<dd>Many projects can share the same object stored in the repository.
	</dl>
<li>The CASE tool can automatically generate project reports (also the acceptance reports at the end of phases) from the content
	of the repository. For example, in MS Visio you can select menu item "Database -&gt; Report" to fire the following wizard:
</ol>

<p align="center"><img border="0" src="https://gakko.pjwstk.edu.pl/materialy/2398/lec/wyklad08/images/8_2.png"></p>

<hr><h3><a name="Przyklad">An example of project documentation <i>Job offers</i></a></h3>


<h4>I. TOR</h4>

<dl>

<dt><b>Project name:</b> <i>Job offers</i>
<dt><b>Context</b>
<dd>In papers and in Internet there are many advertisements of companies
	which 
	offer jobs in IT. PJIIT has many students who want such a job. 
	The authorities of this school would like to have the information on
	the jobs offered by the IT industry.  They are ready to hire a person
	who will enter the offers into the database.
<dt><b>Needs</b>
<dd>The students would be glad to search job offers which meet their particular requirements
	(e.g. the kind of business). The authorities of the school need to know the current trends
	in the job market, because they can have an impact on the new curriculum or the method to teach
	a particular subject.
</dl>


<h4>II. Entity-relationship diagram</h4>

<p align="center"><img src="https://gakko.pjwstk.edu.pl/materialy/2398/lec/wyklad08/images/8_3.png"></p>

<h4>III. List of functions</h4>

<ol>
<li>Add/update/delete information on companies.
<li>Add/update/delete dictionary information:
	<ol type="a">
	<li>categories and kinds of businesses,
	<li>categories and kinds of requirements.
	</ol>	
<li>Enter information on a new offer.
<li>Enter information on the job in an offer.
<li>Update/delete information on offers.
<li>Search offers according to the specified criteria:
	<ol type="a">
	<li>criteria which concern the kind of business,
	<li>criteria which concern the requirements.
	</ol>	
<li>Reports
	<ol type="a">
	<li>the most frequent requirements in offers,
	<li>for each category and kind of business list companies which offer jobs in such
		an area of business;
	<li>for each category and kind of requirement list companies which
		offer jobs with such requirements.
	</ol>	
</ol>

<h4><a name="Podst">IV. Main modules</a></h4>

<ol>
<li>Main control panel (f)
<li>Enter/display companies (f)
<li>Enter offers (f)
<li>Maintain requirements (f)
<li>Backup to floppy (p)
<li>Display offered jobs (f)
<li>Search offers by requirements (f)
<li>Rating of requirements (r)
<li>Report jobs grouped by requirements (r)
</ol>

<h5>Types of modules</h5>

<ul>
<li><b>f</b> = form
<li><b>p</b> = procedure
<li><b>r</b> = report
</ul>

<h4>V. List of modules</h4>


<ol>
<li><b>Main control panel</b> (f)
<dl>
<dt><u>Functions:</u>
<dd>To direct the user to modules which perform required functions. To close the application.
</dl>

<li><b>Enter/display companies</b> (f)
<dl>
<dt><u>Functions:</u>
<dd>To enter/update/display the data on companies
<dt><u>Type:</u>
<dd>Single form
<dt><u>Data source:</u>
<dd>Table <i>Companies</i>
<dt><u>Connections:</u>
<dd>It can be reached from the <i>Main control panel</i> and <i>Enter offers</i>.
</dl>

<li><b>Enter offers</b> (f)
<dl>
<dt><u>Functions:</u>
<dd>To enter information on advertisements, job offers in these advertisements
	and the requirements and duties of each job.
<dt><u>Type:</u>
<dd>Form with subform and pop-up form fired from the subform
<dt><u>Data source:</u>
<dd>Table <i>Offers</i> (the main form), 
	table <i>Jobs in offers</i> (the subform)
	and table <i>Requirements</i> (the pop-up form). A lookup from the main form
	uses data from table <i>Companies</i>.  A lookup from the subform uses
	data from tables <i>Categories of requirements</i> and 
	<i>Kinds of requirements</i>.
<dt><u>Connections:</u>
<dd>It can be reached from the <i>Main control panel</i>. It gives access to
	forms <i>Enter/display companies</i> and
	<i>Maintain requirements</i>.
</dl>

<li><b>Maintain requirements</b> (f)
<dl>
<dt><u>Functions:</u>
<dd>To enter/update/delete/display categories and kinds in the dictionary of requirements.
<dt><u>Type:</u>
<dd>Form with subform.
<dt><u>Data source:</u>
<dd>Table <i>Categories of requirements</i> (the main form) and 
	table <i>Kinds of requirements</i> (the subform)
<dt><u>Connections:</u>
<dd>It can be reached from the <i>Main control panel</i> and <i>Enter offers</i>.
</dl>

<li><b>Backup to floppy</b> (p)
<dl>
<dt><u>Functions:</u>
<dd>To copy the MDB file with the database to a floppy disk.
<dt><u>Type:</u>
<dd>VBA procedure
<dt><u>Connections:</u>
<dd>It can be reached from the <i>Main control panel</i>.
</dl>

<li><b>Display offered jobs</b> (f)
<dl>
<dt><u>Functions:</u>
<dd>To display advertisements which were published after the given date.
<dt><u>Type:</u>
<dd>Form with subform and pop-up form fired from the subform
<dt><u>Data source:</u>
<dd>Query <i>Companies and offers</i> that is the join of tables
	<i>Companies</i> and <i>Offers</i> (the main form),
	table <i>Jobs in offers</i> (the subform) and
	query <i>Categories and requirements</i> that is the join
	of tables <i>Categories of requirements</i>,
	<i>Kinds of requirements</i> and <i>Requirements</i> (the pop-up form).
<dt><u>Connections:</u>
<dd>It can be reached from the <i>Main control panel</i>.
</dl>

<li><b>Search offers by requirements</b> (f)
<dl>
<dt><u>Functions:</u>
<dd>To search offered jobs by the selected requirement which occurred in
	offers published after the given date.
<dt><u>Type:</u>
<dd>Form with subform
<dt><u>Data source:</u>
<dd>Query <i>Everything</i> that is the join of tables
<i>Companies</i>, <i>Offers</i>, <i>Jobs in offers</i>, <i>Categories of requirements</i>,
<i>Kinds of requirements</i> and <i>Requirements</i> (the main form) and
	query <i>Categories and requirements</i> that is the join
	of tables <i>Categories of requirements</i>,
	<i>Kinds of requirements</i> and <i>Requirements</i> (the subform).
<dt><u>Connections:</u>
<dd>It can be reached from the <i>Main control panel</i>.
</dl>

<li><b>Rating of requirements</b> (r)
<dl>
<dt><u>Functions:</u>
<dd>To report the number of times each requirement occurs in offers.
<dt><u>Type:</u>
<dd>Report
<dt><u>Data source:</u>
<dd>Query <i>Rating of requirements</i>
<dt><u>Connections:</u>
<dd>It can be reached from the <i>Main control panel</i>.
</dl>

<li>Report jobs grouped by requirements (r)
<dl>
<dt><u>Functions:</u>
<dd>To report the companies and offered jobs grouped by categories and
	kinds of requirements. 
<dt><u>Type:</u>
<dd>Report
<dt><u>Data source:</u>
<dd>Query <i>Everything</i> that is the join of tables
	<i>Companies</i>, <i>Offers</i>, <i>Jobs in offers</i>, <i>Categories of requirements</i>,
	<i>Kinds of requirements</i> and <i>Requirements</i>
<dt><u>Connections:</u>
<dd>It can be reached from the <i>Main control panel</i>.
</dl>

</ol>

<h5>Ref. 1: The form which implements the module <i>Main control panel</i></h5>

<p align="center"><img src="https://gakko.pjwstk.edu.pl/materialy/2398/lec/wyklad08/images/8_4.png"></p>

<h5>Ref. 3: The form which implements the module <i>Enter offers</i></h5>

<p align="center"><img src="https://gakko.pjwstk.edu.pl/materialy/2398/lec/wyklad08/images/8_5.png"></p>

<h5>Ref. 7: The form which implements the module <i>Search offers by requirements</i></h5>

<p align="center"><img src="https://gakko.pjwstk.edu.pl/materialy/2398/lec/wyklad08/images/8_6.png"></p>

<hr><h3><a name="Organizacja">Microsoft Solutions Framework (MSF)</a></h3>

<p>MSF is a set of guidelines how to conduct a software project.
They are grouped around the fundamental aspects which are formalized
as the following models.</p>

<ol>
<li><i>Risk Management Model</i>
<li><i>Process Model</i>
<li><i>Team Model</i>
<li><i>Enterprise Architecture Model</i>
<li><i>Design Process Model</i>
<li><i>Application Model</i>
</ol>

<hr><h3><a name="Ryzyko">Risk Management Model</a></h3>

<p><i>A risk</i> can be defined as the possibility of loss or injury. 
<i>Proactive risk management</i> involves identifying risks ahead of time and
preventing them through reduction, transference, or avoidance.
The risk management process consists of the following five steps.
</p> 

<ol>
<li>Identify the risk and capture it in <i>the risk statement</i>..
<li>Analyze the risk.
<li>Plan for the risk.
<li>Track the risk.
<li>Control the risk (the risks are mitigated or retired).
</ol>

<p align="center"><img border="0" src="https://gakko.pjwstk.edu.pl/materialy/2398/lec/wyklad08/images/8_7.png"></p>

<hr><h3><a name="Procesy">Process Model</a></h3>

<p><i>Process models</i> establish the order for project
activities from the inception to the scrapping of the system. In this way,
they represent the life cycle of a project. There are different types of process
models in use in business today.</p>

<h4>Waterfall model</h4>

<p>In the waterfall model, each set of tasks must be completed before the next phase
can begin.</p>

<ol>
<li>Such process includes checkpoints called <i><a name="kamien">milestones</a></i>.
	The milestones are points of transition and assessment. They are the basis
	of <i>the task-driven development life cycle</i>.
<li>Usually each phase is performed by a separate team.
<li>Each phase must be thoroughly documented so that the next team have full information.
<li>Critical decisions must be made early.
<li>Testing is the last phase of the project.
<li>Interpersonal communication is limited to written documents (important information
	may be lost; crucial contexts may be forgotten).
<li>User requirements may be buried forever in the tons of documents.
<li>At the beginning the team must focus on the users' needs and not on advantages of
	particular technologies.
</ol>

<h4>Spiral model</h4>

<p><i>The spiral model</i> focuses on the continual need to refine the requirements and
estimates for a project.  This continual need is manifested in <i>iterations</i>, i.e.
repetitions of the cycle in order to refine the product.</p>

<p>The spiral model can be very effective when used for rapid
application development on a very small project. This approach produces great synergy
between the development team and the customer because the customer is involved in all
stages by providing feedback and signing off.</p>

<h4>MSF model</h4>

<p>The MSF process model combines the best principles of the waterfall and spiral
models, deriving the benefits of predictability from the milestone-based planning of
the waterfall model, as well as the benefits of feedback and creativity from the spiral model.</p>

<p>At the milestones check, reviews and synchronization occurs. The milestones
facilitate the assessment and corrections.  They are not frozen dead-ends.</p>

<p>The MSF process model provides a project planning structure which consists of four
distinct phases. Each phase culminates in an externally visible milestone.</p>

<p align="center"><img border="0" src="https://gakko.pjwstk.edu.pl/materialy/2398/lec/wyklad08/images/8_8.jpg"></p>

<h5>MSF milestones</h5>

<p>The MSF process model uses major and interim milestones.
<i>Major milestones</i> mark the transition from one phase to another and
signal transition of project responsibility from one role to another.
Major milestones are times when all team members synchronize 
<i>their deliverables</i> (physical evidence that the team has reached a milestone).
Achieving a major milestone represents team and customer agreement to proceed.

<p><i>Interim milestones</i> indicate early progress and segment large work
efforts into workable and manageable chunks. </p>

<h5>MSF phases</h5>

<p>The following list discusses key activities during the four phases of 
the MSF process model for an enterprise architect project.</p>

<dl>
<dt><b>Phase 1: Envisioning Phase</b>
<dd>During this phase, the team and the customer define the business requirements and
the overall goals of the project. 
The envisioning phase culminates in the vision approved milestone, which indicates that
the team and customer agree on the project direction.

<dt><b>Phase 2: Planning Phase</b>
<dd>During this phase, the team creates a draft of the enterprise architecture plan. 
The planning phase culminates in a project plan approved milestone, in which the
customer of the project approves the enterprise architecture plan. 

<dt><b>Phase 3: Developing Phase</b>
<dd>During this phase, the team moves from project planning into the projects
themselves. The developing phase culminates in the scope complete milestone,
which gives key project members the opportunity to identify and address issues
prior to the release of new technologies and business processes.    

<dt><b>Phase 4: Stabilizing Phase</b> 
<dd>During this phase, the team collects and integrates feedback on the released version,
resolves project-related issues, enhances the enterprise architecture, and prepares
for the next version.   The stabilizing phase culminates in the release milestone, the
formal completion of the current version.

</dl>

<h5>Versioned releases</h5>

<p><i>Versioned releases</i> are a fundamental project technique which divides
large projects into multiple versioned releases.

<ul>
<li>The first release delivers the core product.
<li>Later releases add features incrementally until the product matches the project vision.
<li>The most important features are delivered first.
<li>Versioned releases also enable a project team to respond quickly to changes in scope,
	schedule, and risk during product development.
</ul>

<p align="center"><img border="0" src="https://gakko.pjwstk.edu.pl/materialy/2398/lec/wyklad08/images/8_9.jpg"></p>

<h5>MSF Trade-off Triangle</h5>

<p>The variables in any project are:

<ul>
<li><i>resources</i> (people and money), 
<li><i>schedule</i> (time), and
<li><i>features</i> (the product and its quality). 
</ul>

<p>Those variables can be viewed as having a triangular relationship.  
After the team has established the triangle, any change to one of its variables
(or sides of the triangle) requires a correction to at least one of the variables
to maintain project balance, including, potentially, the same variable
in which the change first occurred.</p>

<p>As the team develops a product, it will inevitably have to make trade-offs among the
project variables. The key to project success is finding the right balance
among resources, schedule, and features.</p>

<p>A project can only be successful if the customer believes that
the team has made the right trade-offs, so the team should ask the
customer about priorities early and often.</p>

<p align="center"><img border="0" src="https://gakko.pjwstk.edu.pl/materialy/2398/lec/wyklad08/images/8_10.jpg"></p>

<h5>Living Documents</h5>

<p>In order to bridge the gap between thinking about a project and doing the project,
MSF uses <i>living documents</i>. IT projects may run the risk of getting caught
in “analysis paralysis,” a condition of endless planning with no action. 
Living documents offer direction and specifics to begin the project, but can be
changed in response to new information or circumstances which 
may surface during the course of a project.</p>

<p>Creating living documents enables a team to arrive at a balance between too
little and too much planning. Living documents are built on the process of determining
a baseline for the document early, but freezing it late: 

<dl>
<dt><i>Baseline early.</i>
<dd>To baseline early means that project teams should create a draft document
	which will be the basis for the complete document as soon as possible
	and move on to developing the solution, even if that means leaving
	some questions unanswered.
<dt><i>Freeze late.</i>
<dd>To freeze late means that as long as the team considers documents to
be dynamic and subject to change, it can add answers and details along the way. 
</dl>

<hr><h3><a name="Zespol">Team Model</a></h3>

<p>The team consists of six roles:</p>

<ol>
<li>product manager,
<li>program manager (project administrator),
<li>developer,
<li>tester,
<li>user educator,
<li>logistics manager.
</ol>

<p align="center"><img border="0" src="https://gakko.pjwstk.edu.pl/materialy/2398/lec/wyklad08/images/8_11.jpg"></p>

<dl>

<dt><b>Product Management</b> involves:
<dd>
<ul>
<li>Leading the team to a shared vision of how to meet customer expectations. 
<li>Acting as the team spokesperson to the customer. 
<li>Developing and maintaining the business case.
<li>Developing and maintaining the communications plan
	(the product manager cares for the communication with the customer and
		for the communications among the members of the team).
</ul>

<dt><b>Program Management</b> involves:
<dd>
<ul>
<li>Coordinating and monitoring the overall process. 
<li>Managing project schedule, resources and limits. 
<li>Ensuring that the team deliver the right product at the right time.
<li>Managing product scope and specification.
<li>Reporting  project status.
<li>Facilitating team communication and negotiation.
<li>Managing the taking of critical trade-off decisions.
</ul>

<dt><b>Development</b> involves:
<dd>
<ul>
<li>Building and testing the product to meet specifications and customer expectations. 
<li>Participating in product design. 
<li>Estimating time and effort to complete the product. 
<li>Serving the team as technology consultants. 
<li>Supporting product installation and deployment.
<li>Developing, configuring, and customizing the product.
</ul>

<dt><b>Testing</b> involves:
<dd>
<ul>
<li>Developing test strategy, plans, and scripts.
<li>Managing the building process. 
<li>Conducting tests. 
<li>Participating in setting the quality bar.
</ul>

<dt><b>User Education</b> involves:
<dd>
<ul>
<li>Teaching end users how to use the product efficiently.
<li>Managing user expectations.
<li>Designing and developing user performance support systems, e.g. reference cards,
	keyboard templates, user manuals, on-line Help, wizards and full-featured course-ware. 
<li>Acting as end-user advocate to the team (communicate the user needs to the team).
<li>Participating in gathering and defining user requirements. 
</ul>

<dt><b>Logistics Management</b> involves:
<dd>
<ul>
<li>Communicating with the IT operations and support.
<li>Ensuring that the product is deployable, manageable and supportable in the future.
<li>Participating in design.
<li>Supporting the product during beta testing. 
<li>Training and supporting operations and personnel for product release. 
</ul>
</dl>

<h4>Team of peers</h4>

<ol>
<li>Shared project vision.
<li>Full cooperation.
<li>Willingness to learn lessons from previous projects.
<li>Individual responsibility, authority, and shared decisions with
	no single prescribed leader.
<li>Common workplace for all.
<li>Breaking of the work into smaller pieces.
</ol>


<h4>Six team goals for success</h4>

<p><table border="1" align="center">
<tr><th>Role			<th>Goal
<tr><td>Product manager		<td>Satisfied customers
<tr><td>Program manager		<td>Delivery within project constraints
<tr><td>Developer		<td>Delivery to product specifications
<tr><td>Tester			<td>Release after addressing all known issues
<tr><td>User educator		<td>Enhanced user performance
<tr><td>Logistics manager	<td>Smooth product deployment
</table></p>

<hr><h3><a name="Archit">Enterprise Architecture Model - BAIT</a></h3>

<p align="center"><img border="0" src="https://gakko.pjwstk.edu.pl/materialy/2398/lec/wyklad08/images/8_12.jpg"></p>

<p>MSF considers <i>four</i> perspectives to enterprise architecture:
business, application, information or data, and technology.
There exists, however, only <i>one</i> architecture for the enterprise.</p>

<p>The acronym <i>BAIT</i> is an easy way to remember the four-in-one concept
of enterprise architecture. 

<ul>
<li><b>B</b><i>usiness</i> is at the top because it drives the enterprise.
<li><b>A</b><i>pplications</i> and 
<li><b>I</b><i>nformation</i> is the means to achieve business goals and objectives of the enterprise.
<li><b>T</b><i>echnology</i> is the engine and platform which support and
	instantiate the other perspectives into a solution. 
</ul>

<h4>Business</h4>

<p>The business perspective describes how the business works.</p>

<dl>
<dt><i>Goals and objectives.</i>
<dd>What is the business of the organization?
<dt><i>Organization.</i>
<dd>Who is responsible?
<dt><i>Business process.</i>
<dd>How does the organization do business?
<dt><i>Customer.</i>
<dd>Who is the target customer?
<dt><i>Suppliers/vendors.</i>
<dd>With whom does the organization need to work?
</dl>

<h4>Applications</h4>

<p>The application perspective describes automated services which support
business processes depicted in the business architecture, and it
describes the interaction and interdependencies of the organization’s
applications. In addition, it provides guidelines for developing new
applications and moving to new application models.</p>

<h4>Information</h4>

<p>The information perspective:</p>

<ul>
<li>describes what the organization needs to know to run its business processes and operations;
<li>specifies where information is stored, moved, and shared throughout the organization;
<li>identifies information origination, ownership, and consumption. 
</ul>

<h4>Technology</h4>

<p>The technology perspective:</p>

<ul>
<li>assesses the current technology base for the enterprise;
<li>establishes standards and guidelines for the acquisition and deployment of: 
	<ul>
	<li>workstation and server tools and base applications, 
	<li>infrastructure services, 
	<li>network connectivity 
	<li>components, and 
	<li>platforms.
	</ul>
<li>defines the technology services needed to carry out the business mission, such as:
	<ul> 
	<li>topologies, 
	<li>development environments, 
	<li>application programming interfaces, 
	<li>security, 
	<li>network services, 
	<li>database management systems, 
	<li>technical specifications, 
	<li>hardware tiers, and 
	<li>operating systems. 
	</ul>
</ul>

<hr><h3><a name="Design">Design Process Model</a></h3>

<p align="center"><img border="0" src="https://gakko.pjwstk.edu.pl/materialy/2398/lec/wyklad08/images/8_13.png"></p>

<p>The MSF component design model structure provides for a continuum 
of design-related project activities through conceptual, logical, and physical design.</p>

<p>The use of the term <i>continuum</i> in this context refers to the process whereby
each design activity (conceptual, logical, and physical) flows into the next activity
and between activities. For example, the output of conceptual design feeds into logical
design, but holes in the logical design may make further conceptual design necessary.
By definition, the implementation of a physical design should be traceable
back to conceptual design.</p>

<dl>
<dt><i>Conceptual Design</i>
<dd>
The conceptual design corresponds to  the rough sketches and scenarios created when designing a house.
<ul>
<li>Identify business need.
<li>Understand what users do and what they require. 
<li>The models used are easily understood and
	 created by the customer and the architect working together.
</ul>


<dt><i>Logical Design</i>
<dd>
The logical design corresponds to   a floor plan and elevation, where elements
	such as spatial relationships are organized.
<ul>
<li>Organize the details of the application which the team builds to fulfill
	business needs and user requirements. 
<li>Lay out the structure of the solution and the communication paths among elements.
</ul>

<dt><i>Physical Design</i>
<dd>
The physical design corresponds to a contractor’s blueprints for the physical
elements of a structure—wiring, plumbing, heating, and ventilation.
The contractor’s plans add detail to the architect’s plans and reflect
real-world construction constraints.

<ul>
<li>Address the technology which will be used by the end user.
<li>Apply real-world technology constraints to the logical design, such as
	implementation and performance considerations.

</dl>

<hr><h3><a name="Apl">Application Model</a></h3>

<dl>
<dt><i>Application</i>
<dd>A logical network of distributed cooperating services.
<dt><i>Service</i>
<dd>An independent unit of application logic within a component which includes
	methods for implementing an operation, function, or transformation. It has a precise
	programming interface which can be used in various execution environments:
	the same machine, another machine connected to the same LAN or any machine on the Internet.
<dt><i>Reuse of services</i>
<dd>The same business solution may be a component of many applications.
</dl>

<p>The MSF application model:</p>

<dl>
<dt><i>Establishes definitions, rules, and relationships.</i>
<dd>
<ul>
<li>Establishes the definitions, rules, and relationships which will form the structure of the application.
<li>Serves as a basis for exchanging ideas during the logical design of an application.
<li>Shows how the application is structured, not how it will be implemented (the emphasis is logical, not physical).
</ul>
<dt><i>Facilitates a consistent approach to application design and development.</i>
<dd>
<ul>
<li>Builds a common understanding of the application.
<li>Defines a working vocabulary for describing application designs.
</ul>

<dt><i>Uses services-based component design.</i>
<dd>
<ul>
<li>An organization may use more than one application model to accommodate
	the different types of applications that it is developing.
<li>The MSF application model uses services-based component design to build applications.
</ul>
</dl>

<h4>Service-based applications</h4>

<p align="center"><img border="0" src="https://gakko.pjwstk.edu.pl/materialy/2398/lec/wyklad08/images/8_14.png"></p>

<p>The services based application model uses a three-tier, logical model 
for designing multi-tier, distributed applications which 
include three broad categories of service:

<ul>
<li><i>user services</i> (squares in the picture above), 
<li><i>business services</i> (triangles), and 
<li><i>data services</i> (circles).
</ul>

<dl>

<dt><i>User Services</i>
<dd>
<ul>
<li>Have an interface which is visual or programmatic, where the user may be a person or another application.
<li>Present information to and gather data from the user.
<li>Hide information views from user interface structures.
</ul>

<dt><i>Business Services</i>
<dd>
<ul>
<li>Ensure integrity of business transactions.
<li>Transform data into information by applying business rules. 
<li>Define the business processes, rules, and workflow which an organization follows.
</ul>

<dt><i>Data Services</i>
<dd>
<ul>
<li>Maintain persistent application data.
<li>Provide the ability to define, create, read, update, and delete.
<li>Hide the design, implementation, and location of data.
</ul>

</dl>

<hr><h3><a name="Podsumowanie">Summary</a></h3>

<p>To design and to implement an information system is never an easy task. 
Most methodologies of software development include the following phases.</p>

<ol>
<li><i>Strategy</i> (initial analysis of the problem)
<li><i>Detailed analysis of the problem</i>
<li><i>Design of the system</i>
<li><i>Implementation of the system</i> (with development of documentation and testing)
<li><i>Deployment of the system</i>
</ol>

<p>During each phase the project team produces the project documentation.
This documentation is usually stored in the specific database, called
<i>the repository</i> which is a part of a CASE tool.</p>

<p>MSF is a set of guidelines how to conduct a software project.
They are grouped around the fundamental aspects which are formalized
as the following models.</p>

<ol>
<li><i>Risk Management Model</i>
<li><i>Process Model</i>
<li><i>Team Model</i>
<li><i>Enterprise Architecture Model</i>
<li><i>Design Process Model</i>
<li><i>Application Model</i>
</ol>

<hr><h3><a name="Slownik">Dictionary</a></h3>

<dl>

<dt><a href="#Analiza">analysis phase</a>
<dd>The initial phase of a project which consists in identifying the components
	that are necessary to develop the information system that supports
	part of a business.  This phase focuses on question "What?" and neglects
	"How?".
<dt><a href="#Proj">design phase</a>
<dd>The phase of a project which is conducted just after the analysis. 
	The goal of it is to convert the results of the analysis to the layout
	of the structure of the target information system. 
<dt><a href="#Dokumentacja">documentation</a>
<dd>A report on the results achieved by the project team.  It contains text documents
	as well as multimedia.
<dt><a href="#kamien">milestone</a>
<dd>The point of assessment of results.  If they are satisfactory, it is also the point of
	the transition to the next activity (or phase).
<dt><a href="#Organizacja">MSF (Microsoft Solutions Framework)</a>
<dd>A development methodology. It is a set of guidelines how to conduct a software project. 
	They are grouped around the following fundamental aspects: risk management, team,
	process, architecture and application.
<dt><a href="#repozytorium">repository</a>
<dd>The database which stores all design objects (also documents) 
	ever developed and used by the whole project team. 
<dt><a href="#Ryzyko">risk</a>
<dd>A possibility of loss or injury.
<dt><a href="#Apl">service</a>
<dd>An independent unit of application logic within a component which
	includes methods for implementing an operation, function, or transformation. 
	It is the fundamental notion of the MSF application model.
	There are three kinds of services: user services, business services 
	and  data services.
</dl>

<hr><h3><a name="Zadania">Exercise</a></h3>

<p>The main assignment for the subject <i>Relational databases</i>
is to do a project.  The result must also include all required documentation.</p>

<ul>
<li>Have you prepared the TOR for your project?
<li>Have you completed the analytical documentation?
<li>Do you use prototyping in your project?
</ul>
