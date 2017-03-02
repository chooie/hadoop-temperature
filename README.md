Hadoop Temperature App
======================
Made using the reference:
[Hadoop: The Definitive Guide](http://hadoopbook.com/)

Install Hadoop locally
----------------------
- `mkdir ~/software`
- `cd ~/software`
- `curl --remote-name http://apache.claz.org/hadoop/common/hadoop-2.7.3/hadoop-2.7.3.tar.gz`
- In your shell runtime configuration file (e.g. ~/.zshrc or ~/.bashrc),
add this:

    ```bash
    # Java
    export JAVA_HOME=$(/usr/libexec/java_home)
    export PATH=$JAVA_HOME/bin:$PATH

    # Hadoop
    export HADOOP_HOME=~/software/hadoop-2.7.3
    export PATH=$PATH:$HADOOP_HOME/bin:$HADOOP_HOME/sbin
    ```

- Refresh your current shell:
    - `source ~/.zshrc`
    - (Use the right .rc file, depending on your shell)

- Check the install worked
    - `hadoop version`

If everything worked correctly you should see some Hadoop version
information.

Running the app
---------------
- `mvn clean install`
- `hadoop jar target/temperature-app-1.0.0.jar com.spotx.temperature.MaxTemperature data/sample.txt output`
- Check the contents of the 'output' directory to see the output from
the map and reduce pipeline:

        cat output/part-r-00000

