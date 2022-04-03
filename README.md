# IDP project
 
for the course Modellering van complexe systemen (B-KUL-G0B23A) at KU Leuven - master computer science


#notes:
##Elevator algorithm:
direction = up or down until no requests are above or below respectively or waiting
-if contains ind and new request along direction
	stop if same direction
	otherwise continue
	
-if contains ind and new request not along direction
	continue with current direction

-if empty and new request
	add new direction = to new request

-if empty and no new request
	wait

direction switches directions when no request are below or at current floor

-if waiting and then multiple requests
	take nearest one
		if tie
			prioritise up

only allowed to move up when it is not on the top floor, and is only allowed to move down when it is not on the bottom floor

the elevator can change directions when it is: waiting | up->down when no higher requests | down->up when no lower requests

##notes on vocabulary:
UnansweredRequest(t, f) will need inertial, cause to change and init
	probl caused by MakeRequest(t, f)

##general

elevator starts at floor 0
probl elevator starts with closed doors
door open = one time unit
door close= one time unit
door close= that 
request answered at t if at the floor door open in t-1 and close at t

no requests = wait 
wait = door closed
unanswered requests = no wait
only 1 elevator exists
an elevator can only be at 1 floor at the time
	possible implicitly provided via ElPosition(Time):Floor
no floor below 0
floor changes only if door closed
no door change and floor change in the same time unit


MakeRequest(t, f ) should only take effect if UnansweredRequest(t, f ) does not hold

#waiting then request on current floor
keep current direction 

#going up then waiting then current floor request + request below
direction up handle current floor -> no other requests -> handle below

#going up then waiting then current floor request + request below + request above 
direction up handle current floor -> handle above requests -> handle below

#going up then waiting then current floor request + request 1 below + request 2 above 
direction up handle current floor -> handle above requests -> handle below

#multiple request on same floor?

#multiple request on same floor back to back

#UnansweredRequest
-added with the correct time
-continue in time
-approved and removed in next time unit

#when can you change directions
standing still -> request
on other requests in current direction


