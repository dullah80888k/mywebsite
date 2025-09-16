pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // لا توجد خطوة بناء حقيقية مطلوبة لملفات HTML, CSS, JavaScript
                // يمكن استخدام هذه المرحلة لتنفيذ أوامر مثل التحقق من الأخطاء (linting)
                echo 'Building the static website...'
            }
        }

        stage('Deploy') {
            steps {
                // استخدم أمر scp لنشر الملفات إلى خادم بعيد.
                // ستحتاج إلى استبدال القيم Placeholder بالمعلومات الخاصة بك.
                echo 'Deploying the website to the remote server...'
                withCredentials([sshUserPrivateKey(credentialsId: 'YOUR_SSH_CREDENTIALS_ID', keyFileVariable: 'SSH_KEY_FILE')]) {
                    sh """
                        scp -i \$SSH_KEY_FILE -r * YOUR_USERNAME@YOUR_SERVER_IP:/path/to/your/webserver/directory/
                    """
                }
            }
        }
    }
}
