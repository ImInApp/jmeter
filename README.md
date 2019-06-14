**Original jmeter repo and docs can be found at https://github.com/apache/jmeter**

#### General usage:

Requirements: We will need the jdk installed, its not installed by default in the vagrant box: `sudo apt-get install default-jdk`

1) Make a backup of your local database if you want to keep it, we will destroy existing data!!

2) Make any changes you want to the fixtures at _Tests/ApiBundle/DataFixtures/Jmeter/Game/_

3) Run the fixtures: "`bin/console imin:initialize --fixtures=Tests/ApiBundle/DataFixtures/Jmeter/Game/ --clear`", currently this will setup 50 games with 10 users. Adjust protocol host anfd port as desired. 

4) Empty the results file (_jmeter/results.json_) if you want clean output.

5) run jmeter from vagrant: _vendor/apache/jmeter/bin_ : "`./jmeter -n -t ../../../../../backend_v2/jmeter/hometest.jmx -l ../logs/test.csv -e -o ../logs/out/ -Jprotocol=http -Jserver=localhost -Jport=80`" or run the gui from windows by starting _vendor/apache/jmeter/bin/jmeter.bat_

6) Get a cup of coffee...