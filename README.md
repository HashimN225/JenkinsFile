<h3>This is a basic Jenkinsfile with when condition and ENVIRONMENT (used the when condition) and also skipping succes due to the when condition</h3>

Building project (HTML file)...
[Pipeline] sh
+ ls
hello.html
hello.py
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage (hide)
[Pipeline] { (Tests)
Stage "Tests" skipped due to when conditional
[Pipeline] getContext
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Deploy)
[Pipeline] echo
