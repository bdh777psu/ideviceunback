# ideviceunback - Decode manifest and copy files into human readable form from ilibmobiledevice's 'idevicebackup2' output

Since iOS 9.3.2 the idevicebackup2 tool has not been able to perform the 'unback' function as Apple removed the facility.

ideviceunback replaces this functionality

Currently in ALPHA development phase.



### Installation:

1. Clone the project
   $ git clone https://github.com/bdh777psu/ideviceunback.git

3. Build it
   $ make

5. Run it!
   $ ./ideviceunback -h
   
   	...or...
   
   $ ./ideviceunback -v -i path/to/backup -o output/path



### Sample usage with [ilibmobiledevice](https://libimobiledevice.org/):

Prerequisite: Install [Homebrew](https://brew.sh/)


1. Install ilibmobiledevice tool and dependencies:
   $ mkdir -p ~/ideviceprobe/limd-build
   $ cd ~/ideviceprobe/limd-build
   $ curl -o ./limd-build-macos.sh -L is.gd/kdT2Nl
   $ bash ./limd-build-macos.sh -n

3. Install ideviceunback from this repo:
   	$ cd ~/ideviceprobe/
	$ git clone https://github.com/bdh777psu/ideviceunback.git
	$ cd ~/ideviceprobe/ideviceunback
	$ make

4. With your iDevice plugged in and paired to your Mac, turn OFF backup encryption
   (follow the on-screen password prompts on your iDevice when needed):
   	$ idevicebackup2 encryption off

5. Perform iDevice backup:
   	$ mkdir ~/ideviceprobe/idevicebackup
	$ idevicebackup2 backup --full ~/ideviceprobe/idevicebackup

6. Unbackup the previous iDevice backup:
	$ mkdir ~/ideviceprobe/ideviceunbacked
	$ cd ~/ideviceprobe/ideviceunback
	$ ./ideviceunback -v -i ~/ideviceprobe/idevicebackup/* -o ~/ideviceunbacked

7. Open the un-backedup contents of your iDevice for inspection:
   	$ open ~/ideviceunbacked/*


