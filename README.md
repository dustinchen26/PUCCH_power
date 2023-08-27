# PUCCH Transmit Power Calculator
online calculate: https://dustinchen26.github.io/PUCCH_power

## Description & example
```
Ref: ETSI TS 138 213 chap 7.2 Physical uplink control channel

● Please enter the following parameters, and then press Calculate to get the PUCCH power calculation result
p0-nominal: -70
mu: 1
Num RB: 1
Pathloss: 32
Delta TF: 5
TPC Adjustment: -2

Calculate
PUCCH Transmit Power:
= p0-nominal + 10*log(2^mu* Num RB )+ Pathloss+ Delta TF + TPC Adjustment
= -70 + 10 * log10(2^1 * 1) + 32 + 5 + -2
= -70 + 3.010 + 32 + 5 + -2
= -31.990

==================================================================================
// p0-nominal=-70, mu=1
1980/03/16 07:59:43.496	[0xB821]	BCCH_DL_SCH / SystemInformationBlockType1
              pucch-ConfigCommon setup : 
                {
                  pucch-ResourceCommon 3,
                  pucch-GroupHopping neither,
                  p0-nominal -70 //p0-nominal=-70
                }
            frequencyInfoDL 
            {
              scs-SpecificCarrierList 
              {
                {
                  subcarrierSpacing kHz30, //mu=1
                }
				
// (806,14) PUCCH, Num RB=1,
07:59:43.645	[0xB883]	NR5G MAC UL Physical Channel Schedule Report
   -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
   |   |                     |       |Carriers                                                                                                                                                          
   |   |                     |       |       |              |                                   |      |PUCCH Data                                                                                      
   |   |                     |       |       |              |                                   |      |     |Per PUCCH Data                                                                            
   |   |                     |       |       |              |                                   |      |     |        |                |                              |      |       |        |        |
   |   |                     |       |       |              |                                   |Dual  |     |Is      |                |                              |      |       |        |        |
   |   |System Time          |Num    |Carrier|              |                                   |Pol   |Num  |Second  |                |                              |Start |Num    |Starting|        |
   |#  |Slot|Numerology|Frame|Carrier|ID     |RNTI Type     |Phychan Bit Mask                   |Status|PUCCH|Phychan |PUCCH Format    |UCI Request BMask             |symbol|Symbols|RB      |Num RB  |
   -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
   |  0|  14|     30kHz|  806|      1|      0|        C_RNTI|                              PUCCH|     0|    1|       0| PUCCH_FORMAT_F1|                  ACK_NACK_RPT|    10|      4|       0|       1|
   
// (806,14) PUCCH, Pathloss=32, Delta TF=5, TPC Adjustment = -2, PUCCH Transmit Power=-31
07:59:43.644	[0xB8D2]	NR5G LL1 FW MAC TX IU Power
         System Frame Number       = 806
         Slot Number               = 14
      Power Info
         -----------------------------------------------------------------------------------
         |   |       |       |CarrierIdType                                                 
         |   |       |       |PUCCH Data                                                   |
         |   |Carrier|Channel|Transmit|        |TPC       |PHR |Delta|PUCCH |PUCCH |Minimum|
         |#  |Id     |Type   |Power   |Pathloss|Adjustment|MTPL|TF   |Number|Format|Power  |
         -----------------------------------------------------------------------------------
         |  0|      0|  PUCCH|     -31|      32|        -2|  23|    5|     1|     1|    -38|

```
