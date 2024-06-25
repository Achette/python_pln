pipeline {
    agent any
    environment {
        PATH = "C:/Users/iache/AppData/Local/Programs/Python/Python312/python.exe:C:/Windows/system32/cmd.exe"
       
    }
    stages {
        stage('Preparação do Ambiente') {
            steps {
                
                echo 'ja instalado'
            }
        }

        stage('Execução do Teste Levenshtein') {
            steps {
                print('Teste...')
                bat 'python levenshtein_teste.py'
                print('Foi...')
            }
        }

        stage('Verificação do Arquivo de Perguntas') {
            steps {
                script {
                    if (fileExists('perguntas.txt')) {
                        echo 'Arquivo perguntas.txt encontrado!'
                    } else {
                        error('Arquivo perguntas.txt não encontrado. Interrompendo o pipeline.')
                    }
                }
            }
        }

        stage('Execução do Chatbot') {
            steps {
                bat 'python chat_bot.py'
            }
        }
    }
}
