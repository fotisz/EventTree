# EventTree
an event tree back office prototype

This R package is used to build  an event tree as a dataframe object. 
A tree is constructed by an initial etree.make() call.  Subsequent addition of 
add... functions build up the tree.  Event tree calculations proceed during the tree construction.

There is no GUI associated with this package, nor is one expected in the R environment. A user is expected
to code scripts defining the tree as a final version.

Output is currently read as a sub-view of the dataframe object holding the tree. Generation of HTML that will
display the event tree utilizing the D3 javascript library is under development.

Example Scripts:


## etree example


etree1<-etree.make(name="conveyor belt fire")

etree1<-addControl(etree1,at=1, prob=.99, severity=.9, name="heat sensor detects")

etree1<-addControl(etree1,at=2, prob=.99, severity=.3, name="valve operates")

etree1<-addControl(etree1, at=5, prob=.7, severity=.3, name="manual firefight", overwrite=TRUE))

etree1<-addOutcome(etree1, at=6, severity=.7, name="operators worst case", overwrite=TRUE)

etree1<-addOutcome(etree1, at=5, severity=.3, name="operators best case")

etree1<-addOutcome(etree1, at=4, severity=.1,name="auto water spray")

etree1[,1:7]
