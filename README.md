What Is a Shared Library in Jenkins?
A shared library in Jenkins is a collection of Groovy scripts shared between different Jenkins jobs. To run the scripts, they are pulled into a Jenkinsfile.

Why Use a Jenkins Shared Library? 
 Developers use shared libraries to avoid writing the same code from scratch for multiple projects. Shared libraries share code across development projects,
thus optimizing the software development life cycle. This drastically cuts down time spent on coding and helps avoid duplicate code.

step1 : create the project in github and follow the standard folder structure and write one grrovy script
step2 : configure that shared lib under manage jenkins
step3 : u can use that shared lib in ur project
configuration:
1. go to manage jenkins
2.then configure systems
3.search for Global Pipeline Libraries
---> Name - choice of urs
--->Default version - branch or tags which u r using
---> provide git url and save it

create a pipeline job and in pipeline section 
import that library in order to use fucntions in that shared libarary as below

@Library('javahome-demo')     ###here javahome-demo is name of the library u configured under manage jenkins
pipeline{
    agent any
    stages{
        stage('Demo'){
            steps{
                welcome("Nousheen")
            }
        }
    }
}


