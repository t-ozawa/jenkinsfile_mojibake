pipeline {
    agent {
        label 'master'
    }
    environment { 
        hoge = 'envhogedefault'
    }
    parameters {
        string(name: 'strpara', defaultValue: 'strparadefault',description: '説明')
    }
    stages {
        stage('Stage1') {
            steps {
                echo 'S1'
                //シングルコーテーションでは変数使えない
                echo "strpara: ${strpara}"
                echo "envhoge: ${hoge}"
                bat "echo strpara: ${strpara}"
                /*
                //Gitでビルド対象を取得・Gitリポジトリの指定
                //git url: 'git@github.com:t-ozawa/Hellohoge.git', branch: 'master' 
                */
            }
        }
        stage('Stage2') {
            steps {
                echo 'S2'
                /*
                //MSBuildでビルド
                //bat '"C:\\Program Files (x86)\\Microsoft Visual Studio\\2017\\BuildTools\\MSBuild\\15.0\\Bin\\MSBuild.exe" C:\\Jenkins\\workspace\\DemoPipeline20181029\\ConsoleApp_Hellohoge\\ConsoleApp_Hellohoge.sln'
                */
                echo 'ビルド'
                //MSBuildのファイルパス
                //"C:\\Program Files (x86)\\Microsoft Visual Studio\\2017\\Community\\MSBuild\\15.0\\Bin\\MSBuild.exe"
                //slnファイルのパス
                //"C:\\Users\\wosco43-user\\Desktop\\Hellohoge日本語検証\\ConsoleApp_Hellohog\\Hellohoge_日本語検証.sln"
                
                //1
                //bat 'chcp 65001 && "C:\\Program Files (x86)\\Microsoft Visual Studio\\2017\\Community\\MSBuild\\15.0\\Bin\\MSBuild.exe" C:\\Users\\wosco43-user\\Desktop\\Hellohoge日本語検証\\ConsoleApp_Hellohog\\Hellohoge_日本語検証.sln'
                //2
                //chcp 932
                /*
                bat """
                nkf -g C:\\Users\\wosco43-user\\Desktop\\Hellohoge日本語検証\\ConsoleApp_Hellohog\\Hellohoge_日本語検証.sln
                '"C:\\Program Files (x86)\\Microsoft Visual Studio\\2017\\Community\\MSBuild\\15.0\\Bin\\MSBuild.exe" C:\\Users\\wosco43-user\\Desktop\\Hellohoge日本語検証\\ConsoleApp_Hellohog\\Hellohoge_日本語検証.sln'
                """
                */
                
            }
        }
        stage('Stage3') {
            steps {
                echo 'S3'
                /*
                //実行したジョブのworkspaceがカレントディレクトリになっているので注意(Jenkins特有のScript実行時のみ)
                //成果物の保存(これをしないとビルドされたもの(*.exe)が保存されない)
                //archiveArtifacts artifacts: 'ConsoleApp_Hellohoge\\x64\\Debug\\**.exe', onlyIfSuccessful: true
                //成果物ファイルの移動
                //bat 'copy C:\\Jenkins\\workspace\\DemoPipeline20181029\\ConsoleApp_Hellohoge\\x64\\Debug\\ConsoleApp.exe  C:\\Jenkins\\workspace\\DemoPipeline20181029\\ConsoleApp_Hellohoge'
                */
                //成果物の保存
                
            }
        }
    }
}