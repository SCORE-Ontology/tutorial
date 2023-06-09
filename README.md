
# Tutorial to Define a secure-by-design system using our Ontology

Then we have to consider security at the requirements specification stage
# The security criteria ontology:
The security criteria ontology serves as a support for the specification of security requirements in different domains. The aim is that requirement engineers use the ontology as a guide to specifying additional security requirements. This step helps increase the security coverage of the requirements.

For that, we have defined the following **core ontology** in which:

- A security mechanism belongs to one domain or more.
- A security criterion is enforced by one security mechanism or more.
- A security criterion is linked to other security criteria (not itself) using the relationships: ensures, precedes, isAppliedBy, provides, conserves, testsFor, revokes, and contributesTo.

![Figure 1](./figures/figure1.png?raw=true "Figure 1 Generic Ontology in Protege")

The **relationships** are divided into three priorities:

|**Priority**|**Relationships**|
| - | - |
|**High**|Ensures, precedes, isAppliedBy|
|**Medium**|Provides, conserves, testFor|
|**Low**|Revokes, contributesTo|

Then we populated the core ontology and achieved the following **security criteria ontology**

![Figure 2](./figures/figure2.png?raw=true "Figure 2 Generic Ontology Concepts")

The **concepts** of this ontology are security criteria, where a security criterion is a property that needs to be preserved so that the system stays secure, for example: Confidentiality, Integrity, Availability…

The relationships between these criteria make defining additional security requirements possible.

# Web Interface:
We implemented the ontology using protégé (an ontology editor). Then, we created an API that provides access to the ontology.
After that, and to consume the API, we created a web interface that facilitates the use of the security criteria ontology.

![Figure 3](./figures/figure3.png?raw=true "Web interface")

1. To use the ontology, click on Use Ontology in the navigation bar or on USE NOW in the USE THE ONTOLOGY card.
![Figure 4](./figures/figure4.png?raw=true "Web interface")
2. Then choose the domain, the results are the security criteria in the domain according to our research so far
![Figure 5](./figures/figure5.png?raw=true)
3. If you click on one of the security criteria, you will have two choices: to see the security mechanisms of this criterion or to see the additional criteria.
![Figure 6](./figures/figure6.png?raw=true)
4. If you are writing only one requirement with the chosen security criteria, you would want to click the security mechanisms 
![Figure 7](./figures/figure7.png?raw=true)
5. If you need to write the additional security requirements, then you would want to click on additional criteria
![Figure 8](./figures/figure8.png?raw=true)
6. If you need the additional criteria related strictly to the security criterion chosen, you would want to choose All Additional Criteria to get the criteria with all priorities, High Priority Additional Criteria to get only the criteria with high priority, Medium Priority Additional Criteria to get only the criteria with medium priority, or Low Priority Additional Criteria to get only the criteria with low priority.
![Figure 9](./figures/figure9.png?raw=true)

7. However, if you want to get the tree of all additional security criteria and not only the ones directly related to the chosen security criteria, you would want to choose  Additional Criteria Tree. 
![Figure 7](./figures/figure1_7.png?raw=true)

8. Then, to get the security mechanisms of each criterion, click on it in the tree
![Figure 8](./figures/figure1_8.png?raw=true)

# Example: Banking System

You are a requirement engineer working on a banking system. You are mainly concerned about the security aspects of the system. Your highest priority is that the system preserves the privacy of the clients. To define privacy and its additional security criteria, you can follow the steps below:

**Go to <http://193.52.45.42:8787/>** 
1. Go to the use ontology page.
![Figure 4](./figures/figure4.png?raw=true "Web interface")
2. Choose the banking domain.
![Figure 10](./figures/figure10.jpg?raw=true "Web interface")

3. Since we are concerned about privacy, choose the privacy security criterion.
![Figure 11](./figures/figure11.png?raw=true "Web interface")

4. To see the additional criteria that can be defined to enforce privacy, choose Additional Criteria.
![Figure 12](./figures/figure12.png?raw=true "Web interface")
![Figure 13](./figures/figure13.png?raw=true "Web interface")

5. Then choose additional criteria tree. 
![Figure 14](./figures/figure14.png?raw=true "Web interface")

6. To see the security mechanisms of each criteria, click on it.
![Figure 15](./figures/figure15.png?raw=true "Web interface")

7. Then using this tree, the table, and the template given below, we define the security requirements for privacy, confidentiality, and access control.
![Figure 16](./figures/figure16.png?raw=true "Web interface")

Template: The system <word> <verb> the <security criteria> of the user’s data by <security mechanism>

1. SR-SYS-PR-01 : The system SHALL guarantee the privacy of user’s data by Attribute Based Access Control.
![Figure 17](./figures/figure17.png?raw=true "Web interface")

1.1. SR-SYS-CO-01: The system SHALL guarantee the confidentiality of user’s data by Symmetric Encryption.
![Figure 18](./figures/figure18.png?raw=true "Web interface")

**Confidentiality ensures privacy. Then, according to the table, the priority word to use is SHALL and the verb is guarantee.**

1.1.1 SR-SYS-AN-01: The system COULD grant the anonymity of user’s data by Anonymous Communication System
![Figure 19](./figures/figure19.png?raw=true "Web interface")

1. SR-SYS-AC-01: The system SHALL guarantee the access control of user’s data by challenge response.
![Figure 20](./figures/figure20.png?raw=true "Web interface")

# Conclusion

Using the ontology and its web interface we were able to define not only one security requirement but its additional security requirements that help enforce the security criteria and increase the security coverage in a system. In the example given, we were concerned about confidentiality. We first defined a confidentiality security requirement (with a relevant security mechanism). Then we explored the criteria tree of confidentiality where we defined additional security requirements using the criteria in the tree, their relationships, and their security mechanisms.
