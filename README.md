Download Link: https://assignmentchef.com/product/solved-cs-52-assignment-5-project-2-record-player
<br>
Following the class diagram shown below, create the class RecordPlayer. An RecordPlayerrepresents a stereo component that can play vinyl records. Please review the class and the sample driver code. There is a specific order to the way the class methods should be called. In other words, you can’t plop the Needle unless there actually is a record on the player and the recordplayeris turned on. You also can’t return the Needle unless there is actually a record on the player and the recordplayeris turned on. Your class should enforce these rules and write errors to cout as they occur. A sample driver for this class is shown below.

Rules of the record player

<ol>

 <li>You can affix a platter if the record player is on or off and the needle is not ploped</li>

 <li>Record player must be on and must have record affixed to the platter to plop the needle on the record</li>

 <li>Can only return the needle if the record player is on and there is a record on the player</li>

 <li>Performing the same action twice results in a “no-op” where nothing changes. For example, you can’t plop an already plopped needle, and you can’t return a needle that’s already returned. Another example: you can’t turn on/off a record player that is already on</li>

</ol>

<strong>Please note: codeboard must test differently for this project. There is no input. The provided driver will be called automatically. Your code will not compile when you start the project; only when you’ve implemented the RecordPlayer class will it compile successfully.</strong>

Record Player

<pre>RecordPlayer( );void turnOn( );void turnOff( );bool isPoweredOn( );void affixPlatter( string record );void plopNeedle( );void returnNeedle( );bool isOn;string record;bool needleIsOnTheRecord;</pre>

Record Player Sample Driver Code

<pre>//declare 6 RecordPlayersRecordPlayer good_r, bad_r1, bad_r2, bad_r3, bad_r4, bad_r5;//first test correctgood_r.turnOn();good_r.affixPlatter("Barrow Manila I");good_r.plopNeedle();good_r.returnNeedle();good_r.turnOff();//bad test, plops needle without turning it on or putting record onbad_r1.plopNeedle();//turns it on but no record on platterbad_r2.turnOn();bad_r2.plopNeedle();//not on nor has album on platterbad_r3.returnNeedle();//turned on but no albumbad_r4.turnOn();bad_r4.returnNeedle();//not turned onbad_r5.affixPlatter("Barrow Manila I");bad_r5.plopNeedle();</pre>

Record Player Sample Driver Code Output

<pre>Record player is turned onRecord Barrow Manila I is now on the platterNeedle is placed on the recordNeedle is returned from the recordRecord player is turned offCannot place needle on the recordRecord player is turned onCannot place needle on the recordCannot return needle from the recordRecord player is turned onCannot return needle from the recordRecord Barrow Manila I is now on the platterCannot place needle on the record</pre>