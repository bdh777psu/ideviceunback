# ideviceunback - Decode manifest and copy files into human readable form from ilibmobiledevice's 'idevicebackup2' output

Since iOS 9.3.2 the idevicebackup2 tool has not been able to perform the 'unback' function as Apple removed the facility.

ideviceunback replaces this functionality

Currently in ALPHA development phase.



### Installation:

1. Clone the project<br>
   $ git clone https://github.com/bdh777psu/ideviceunback.git

3. Build it<br>
   $ make

5. Run it!<br>
   $ ./ideviceunback -h<br>
   
   	...or...<br>
   
   $ ./ideviceunback -v -i path/to/backup -o output/path<br><br>



### Sample usage with [ilibmobiledevice](https://libimobiledevice.org/):

Prerequisite: Install [Homebrew](https://brew.sh/)<br>


1. Install ilibmobiledevice tool and dependencies:<br>
   $ mkdir -p ~/ideviceprobe/limd-build<br>
   $ cd ~/ideviceprobe/limd-build<br>
   $ curl -o ./limd-build-macos.sh -L is.gd/kdT2Nl<br>
   $ bash ./limd-build-macos.sh -n<br><br>

3. Install ideviceunback from this repo:<br>
   	$ cd ~/ideviceprobe/<br>
	$ git clone https://github.com/bdh777psu/ideviceunback.git<br>
	$ cd ~/ideviceprobe/ideviceunback<br>
	$ make<br><br>

4. With your iDevice plugged in and paired to your Mac, turn OFF backup encryption<br>
   (follow the on-screen password prompts on your iDevice when needed):<br>
   	$ idevicebackup2 encryption off --interactive<br><br>

5. Perform iDevice backup:<br>
   	$ mkdir ~/ideviceprobe/idevicebackup<br>
	$ idevicebackup2 backup --full ~/ideviceprobe/idevicebackup<br><br>

6. Unbackup the previous iDevice backup:<br>
	$ mkdir ~/ideviceprobe/ideviceunbacked<br>
	$ cd ~/ideviceprobe/ideviceunback<br>
	$ ./ideviceunback -v -i ~/ideviceprobe/idevicebackup/* -o ~/ideviceprobe/ideviceunbacked<br><br>

7. Open the un-backedup contents of your iDevice for inspection:<br>
   	$ open ~/ideviceprobe/ideviceunbacked/<br>


