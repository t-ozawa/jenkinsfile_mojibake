pipeline {
    agent {
        label 'master'
    }
    environment { 
        hoge = 'envhogedefault'
    }
    parameters {
        string(name: 'strpara', defaultValue: 'strparadefault',description: '����')
    }
    stages {
        stage('Stage1') {
            steps {
                echo 'S1'
                //�V���O���R�[�e�[�V�����ł͕ϐ��g���Ȃ�
                echo "strpara: ${strpara}"
                echo "envhoge: ${hoge}"
                bat "echo strpara: ${strpara}"
                /*
                //Git�Ńr���h�Ώۂ��擾�EGit���|�W�g���̎w��
                //git url: 'git@github.com:t-ozawa/Hellohoge.git', branch: 'master' 
                */
            }
        }
        stage('Stage2') {
            steps {
                echo 'S2'
                echo '�r���h'

                //chcp 65001
                bat """
                chcp 65001
                "C:\\Program Files (x86)\\Microsoft Visual Studio\\2017\\Community\\MSBuild\\15.0\\Bin\\MSBuild.exe" C:\\Users\\Administrator\\Desktop\\hoge���{�ꌟ��\\hoge���{�ꌟ��\\hoge���{�ꌟ��.sln
                """
            }
        }
        stage('Stage3') {
            steps {
                echo 'S3'
                /*
                //���s�����W���u��workspace���J�����g�f�B���N�g���ɂȂ��Ă���̂Œ���(Jenkins���L��Script���s���̂�)
                //���ʕ��̕ۑ�(��������Ȃ��ƃr���h���ꂽ����(*.exe)���ۑ�����Ȃ�)
                //archiveArtifacts artifacts: 'ConsoleApp_Hellohoge\\x64\\Debug\\**.exe', onlyIfSuccessful: true
                //���ʕ��t�@�C���̈ړ�
                //bat 'copy C:\\Jenkins\\workspace\\DemoPipeline20181029\\ConsoleApp_Hellohoge\\x64\\Debug\\ConsoleApp.exe  C:\\Jenkins\\workspace\\DemoPipeline20181029\\ConsoleApp_Hellohoge'
                */
                //���ʕ��̕ۑ�
                
            }
        }
    }
}