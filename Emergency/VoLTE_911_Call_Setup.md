### Option 1 ####
participant UE 
participant SBG
participant E-CSCF
participant LRF
participant I-CSCF
participant S-CSCF
participant MTAS
participant IBCF
participant "IMS B# PSAP" as PSAP




UE -> SBG: INVITE:SOS (AUDIO+RTT)
SBG -> E-CSCF: INVITE:SOS (AUDIO+RTT) 
E-CSCF -> LRF: INVITE:SOS (AUDIO+RTT)
E-CSCF <- LRF: 300MC (IMS B#)
box over LRF #white:<color:#black> LRF will translate \n the source cell into IMS B#
E-CSCF -> I-CSCF: INVITE B# (AUDIO+RTT)
I-CSCF -> S-CSCF: INVITE B# (AUDIO+RTT)
S-CSCF <-> MTAS: SIP INVITE B# (AUDIO+RTT)
S-CSCF -> IBCF: INVITE B# (AUDIO+RTT)
rbox over User,PSAP #white: Call setup SIP (183, PRACK, 200OK)



