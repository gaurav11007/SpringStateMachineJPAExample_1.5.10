# SpringStateMachineJPAExample_1.5.10
Spring stateMachine Persisit Example Spring version spring boot 1.5.10 &amp; spring stateMachine 1.2.8

This eample is a simple working example of persisting state machine into Database and fetch it back to reset the state machine.

Two API provided.

1)

http://localhost:8085/StateMachine/init

Content-Type : application/json

Payload : 
          {
            "machineid" : "11"
          }
          
This request will create statemachine with machineId as "11" & Initialize it to initial State "I" and persist it Database ( table : state_machine )          
          
2) 

http://localhost:8085/StateMachine/proceed

Content-Type : application/json

Payload : 
          {
            "machineid" : "11",
            "event": "E1"
          }
          
This request will find stateMachine in DB against given machine ID and if found it will use persisted stateMachine context to
create stateMachine instance to the state as it was persisted earlier. If fail to find will return new instance initialized to its given 
initial state.


# Note : Dont forget to change DB details ( User -password, DB name in application.properties )
