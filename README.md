When AWS released Custom Runtimes, some nice person [1] created a Lambda Layer to run Bash. I had been waiting for this day since Bash is my preferred language.
I started to automate and move all my home based scripts to Lambda.
When AWS announced they were moving Lambda to Amazon Linux 2, the layer no longer functioned.
I reached out to gkrizek, but he was not going to update, so I created a new Lambda Layer that would allow me to continue to work.

All the requirements and issues that were in gkrizek's version still apply, check that out for the details.

In addition, if you need to run any AWS CLI commands, you will need these variables set properly:

    export PYTHONPATH="/opt/lib/:/opt/lib/python/:/opt/lib/awscli/:/opt/lib/python/lib-dynload"
    export PYTHONHOME="/opt/"
    export LD_LIBRARY_PATH="$LD_LIBRARY_PATH:/opt/lib/python/lib-dynload"

[1] https://github.com/gkrizek/bash-lambda-layer
