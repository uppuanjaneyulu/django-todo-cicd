pipeline {
	agent any
		
	stages{
		stage('Checkout') {
			steps {
				git url: "https://github.com/uppuanjaneyulu/django-todo-cicd.git", branch: 'develop'
			}
		}
		stage('Build') {
			steps {
				sh 'docker build -t uppuanji/django-app-img:v1 . '
			}
		}
		stage('Test') {
			steps {
				echo "Tesing"
			}
		}
		stage('Deploy') {
			steps {
				sh 'docker run --rm -d --name nginx01 -p 8000:8000 uppuanji/django-app-img:v1'
			}
		}
	}
}
