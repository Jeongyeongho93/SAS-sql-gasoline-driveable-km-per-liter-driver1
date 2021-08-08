# gasoline-driveable-km-per-liter-driver1

DATA gasoline;
  DO driver = 1 TO 4;
     DO car = 1 TO 4;
        INPUT gas $ km @; OUTPUT;
     END;
  END;
DATALINES;
D 15.5 B 33.9 C 13.2 A 29.1
B 16.3 C 26.6 A 19.4 D 22.8
C 10.8 A 31.1 D 17.1 B 30.3
A 14.7 D 34.0 B 19.7 C 21.6
;
RUN;

PROC PRINT DATA = gasoline;
RUN;

PROC SQL OUTOBS=4;
SELECT * FROM gasoline;
WHERE driver in ('1') AND car between '1' and '4';
QUIT;
RUN;
