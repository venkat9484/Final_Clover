#!groovy

import java.util.Collections

// Valid Jenkins versions for test
def testJenkinsVersions = [ '2.235.1', '2.235.2', '2.235.3', '2.235.4','2.235.5', '2.249.1', '2.249.2', '2.263', '2.264', '2.267', '2.268' ]
Collections.shuffle(testJenkinsVersions)

// build recommended configurations
subsetConfiguration = [ [ jdk: '8',  platform: 'windows', jenkins: testJenkinsVersions[0], javaLevel: '8' ],

                        // Intel Linux is labeled as 'linux' for legacy reasons
                        [ jdk: '8',  platform: 'linux',   jenkins: testJenkinsVersions[1], javaLevel: '8' ],
                        [ jdk: '11', platform: 'linux',   jenkins: testJenkinsVersions[2], javaLevel: '8' ],

                        // ARM label is Linux also
                        [ jdk: '8',  platform: 'arm64',   jenkins: testJenkinsVersions[3], javaLevel: '8' ],

                        // PowerPC 64 and s390x labels are also Linux
                        // [ jdk: '8',  platform: 'ppc64le', jenkins: testJenkinsVersions[4], javaLevel: '8' ],
                        [ jdk: '11', platform: 's390x',   jenkins: testJenkinsVersions[5], javaLevel: '8' ],
                      ]

buildPlugin(configurations: subsetConfiguration, failFast: false)
