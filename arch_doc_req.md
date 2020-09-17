
Scope
=====
This document intends to capture the requirements of a system architecture document. 
The intent is to evolve an architecture document template for documenting various systems we build at Amagi.

Assumption
==========
 A requirement document for the software system is available.

System Architecture Document Requirements
=========================================

A system architecture document is living document through out the development of the software system. 
The document needs to evolve along with the system that it is describing. 

An architecture document should have the following:

1. Brief scope describing the software system with reference to requirements
   document.

2. Glossary: Definitions of various concepts/nouns used in the system

3. Identify various components and list them

   Note: A component is a runtime entity. E.g. a microservice, a process, a
   group of processes, a database etc. A library e.g. a mathlibrary used is not
   a runtime component we are interested here.

4. For each component define interfaces at different stages of components life
   - Init Time
   - Run Time
   - Teardown time

    Interfaces encompass the following
      - Verbs to describe functionality
      - Data model described the data coming in and going out of component
      - Data model for data store component
      - Metrics to observe the system (observability)
      - Data model for any configuration required by component

   These details will largely cater to the architectural elements **components** and **data** described in reference [1].

   Note: Data model need not be detailing every aspect but in terms of concepts
   and attributes described in glossary

   Note: Architectural viewpoints to be added as per secion 1.7 of reference [1]. TBD

5. Define relationship between the components above. A brief on every pair of
   component that interacts and the mechanism of interation. This is the connector aspect disccuess in reference [1].

6. Software system from user perspective. How will a end user use this system to
   get something done? Is there a commandline interface, UI or web interface.

7. Usecase scenarios. Enumeration of typical usecases of the system. Typical user workflows to be enumerated.

8. Enumerate architectural properties to be maintained. We need to evolve the set of properties. E.g.
   - Single tenant or multitenanted system
   - Self healing  i.e. if a component dies it should come back to  running
     state on its own
   - Scalability
   - High availability


Documentation Management
========================

1. Checkin all system architecture documents in a common amagi-architectures git repo.

2. Each git repository implementing a part of the system points to the arch document in the landing README.md of the repository.


References
==========

1. Architectural Styles and the Design of Network-based Software Architectures, Roy Fielding

=====================

As the document evolves over time, it might be good to include some information
about technology chosen to implement and some rationale especially when multiple
contenders were evaluated to arrive at a choice.
