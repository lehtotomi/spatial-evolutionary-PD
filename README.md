# spatial-evolutionary-PD
Deterministic spatial evolutionary prisoner's dilemma model in NetLogo

How to use it?
This model can be used in the NetLogo environment or in the NetLogo Web environment. 
To use model in the NetLogo Web just go to NetLogo Web and use the Upload a Model button.
However the performance in NetLogo Web seems to be poor and some features don't work correctly, but using it can give quick overview about this model. 

The info tab of the model:
## WHAT IS IT?

This model is deterministic and more feature rich model of Wilensky(2002) NetLogo PD Basic Evolutionary model. The original model was non-deterministic in the sense that state resulting from earlier state was dependent on random factors. In this deterministic model these random elements have been removed, which enables closer studying of micro level behaviour. In this model there is also added feature to "draw" states, which enables studying of certain patterns of interest.

In this model patches gain score based on their strategies. Patches with strategy cooperate gain 1 point for each patch in their neighbourhood which also has strategy cooperate. Patches with strategy defect gain point equal to b*c where b is the defection-award and c is the number of patches with strategy defect in patches neighbourhood. After each tick the patches calculates their scores according to their neighbourhood and then obtain the strategy of patch with highest score in it's neighbourhood. The neighbourhood size is 8 and the patch is not itself included in it's own neighbourhood. By default the topology is closed. Ties are broken in favour of cooperate strategy.

The color coding of strategies is equal to:
cooperate = blue, defect = red, changed from defect to cooperate = yellow ,changed from cooperate to defect = green.

Wilensky, U. (2002). NetLogo PD Basic Evolutionary model. http://ccl.northwestern.edu/netlogo/models/PDBasicEvolutionary. Center for Connected Learning and Computer-Based Modeling, Northwestern University, Evanston, IL

## HOW IT WORKS

There were two reasons for non-deterministic behaviour:
1. NetLogo determines randomly the order in which patches respond when they are asked. This resulted to behaviour were wrong stategy was selected if patch with highest score in it's neighbourhood changed strategy before some of it's neighbour had obtained strategy from it. This behaviour was non-deterministic because the order in which patches chose stategy was random.

2.According to netLogo documentation the max-one-of function breaks ties randomly. in the cases of rear ties this behaviour can results in random non-deterministic behaviour.

The changes to make the model deterministic are presented in the NetLogo features section.

## HOW TO USE IT

Press setup to setup the model. The initial-cooperation determines the probability that a patch begins with strategy cooperate. Press go to advance one tick and continues go to abvance repeatedly. To draw initial state select 100% initial-cooperate or 0% initial-cooperate and use the draw buttons to draw wanted initial state. It should be noticed that to see what is drawn before eny go actions are called the view updates should be set to continues. When the model is running the on ticks option can be preferred because it show the states as indented by this model.

Use the defection-award slider to change defection award.

## THINGS TO NOTICE

It should be noticed that to see what is drawn before eny go actions are called the view updates should be set to continues.

## THINGS TO TRY

This model enables to study how defection-award affects different states. As such you can play around with the defection-award slider and different kind of initial states.

## EXTENDING THE MODEL

Many more features could be added. For example features to enable statistical analysis and adding of more complicated strategies or some kind of introduction of pay-off matrixes. Also some different kind of rules related to neighbourhoods, topology etc can be explored.

## NETLOGO FEATURES

The problem 1 is solved by introducing cooperate-calc? variable which acts as an indicator wheather or not the patch has already performed select-stategy funtion. This variable enables select-stategy to check if it should use it's highest score neighbour's cooperate? or old-coopertate? variable. When the function functions this way it enables it to allways use the strategy patches have before each tick, which eliminates the 1. source of non-deterministic behaviour.

The problem 2 is simply solve by use of to-report, which enables us to specify how the ties should be broken. In this model it is decided that ties are allways broken in favour of cooperete stategy.

## RELATED MODELS

Wilensky, U. (2002). NetLogo PD Basic Evolutionary model. http://ccl.northwestern.edu/netlogo/models/PDBasicEvolutionary. Center for Connected Learning and Computer-Based Modeling, Northwestern University, Evanston, IL

## CREDITS AND REFERENCES
This model was created by Tomi Lehto in 2020.

This model is based on and inspired by Wilensky(2002) PD Basic Evolutionary model. Copyright 2002 Uri Wilensky. The original model is licensed under the Creative Commons Attribution-NonCommercial-ShareAlike 3.0 License.
https://creativecommons.org/licenses/by-nc-sa/3.0/

Because of this this model is also distributed under
Creative Commons Attribution-NonCommercial-ShareAlike 3.0 License
https://creativecommons.org/licenses/by-nc-sa/3.0/
This model is not endorsed in anyway by the creator of the original model.

Sitation for the original model:
Wilensky, U. (2002). NetLogo PD Basic Evolutionary model. http://ccl.northwestern.edu/netlogo/models/PDBasicEvolutionary. Center for Connected Learning and Computer-Based Modeling, Northwestern University, Evanston, IL
