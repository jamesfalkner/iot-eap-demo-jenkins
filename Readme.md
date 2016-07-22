#jenkins
Custom Jenkins instance to do CI/CD builds for IOT demo

To update your plugins.txt
--------------------------

    export JENKINS_HOST=admin:password@[hostname of route for jenkins server]
    curl -k -sSL "https://$JENKINS_HOST/pluginManager/api/xml?depth=1&xpath=/*/*/shortName|/*/*/version&wrapper=plugins" | perl -pe 's/.*?<shortName>([\w-]+).*?<version>([^<]+)()(<\/\w+>)+/\1 \2\n/g'|sed 's/ /:/' > plugins.txt



