This is my curent configuration which I use with CRIUS SE, Frsky telemetry and EZ-GUI.
There are two commands added to the serial protocol and few other modifications.

Added commands:
#define MSP_SET_SERIAL_BAUDRATE 199 //in message   serial 0 boud rate
#define MSP_ENABLE_FRSKY 198 //in message no parm

   case MSP_SET_SERIAL_BAUDRATE: 
      if(!f.ARMED){
        SerialOpen(0,read32());
      }
      headSerialReply(0);
     break;
   
   case MSP_ENABLE_FRSKY:
     FrskyEnabled=true;
    break;
