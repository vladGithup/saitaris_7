new read me file
mogkrpvm



        <!--<project name="saitaris_9" basedir="." default="all">
        <property name="src.dir" value="src"/>
        <property name="build.dir" value="build"/>
        <property name="classes.dir" value="${build.dir}/classes"/>
        <property name="jar.dir" value="${build.dir}/jar/"/>
        <property name="jar.name" value="${jar.dir}/saitaris_9.jar"/>
        <property name="junit.jar" value="lib/junit-4.13.2.jar"/>

        <target name="clean">
            <delete dir="${build.dir}"/>
        </target>

        <target name="compile" depends="clean">
            <mkdir dir="${classes.dir}"/>
            <javac srcdir="${src.dir}" destdir="${classes.dir}" includeantruntime="false">
                <classpath>
                    <pathelement path="${junit.jar}"/>
                </classpath>
            </javac>
        </target>

        <target name="run" depends="compile">
            <java classname="com.example.HelloWorld" fork="true" classpath="${classes.dir}"/>
        </target>

        <target name="jar" depends="compile">
            <mkdir dir="${jar.dir}"/>
            <jar destfile="${jar.name}" basedir="${classes.dir}"/>
        </target>

        <target name="test" depends="compile">
            <mkdir dir="${build.dir}/test-results"/>
            <junit printsummary="on" haltonfailure="true" fork="true" showoutput="true">
                <classpath>
                    <pathelement path="${classes.dir}"/>
                    <pathelement path="${junit.jar}"/>
                </classpath>
                <batchtest todir="${build.dir}/test-results">
                    <fileset dir="${src.dir}/com/example/test">
                        <include name="**/*Test.class"/>
                    </fileset>
                </batchtest>
                <formatter type="plain"/>
            </junit>
        </target>

        <target name="all" depends="run, jar, test">
            <echo message="Build complete! Run and JAR created successfully."/>
        </target>
        </project>