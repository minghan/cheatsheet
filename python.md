Python Tricks
=============

HTTP Server serving current directory

    python -m SimpleHTTPServer 8000

Fake SMTP server for testing/debugging

    python -m smtpd -n localhost:5000

Pretty print JSON

    echo '{"key":"val"}' | python -m json.tool
    python -m json.tool  file.json

Profiling python app

    python -m cProfile app.py

virtualenv

    virtualenv --system-site-packages ~/py-env
    source ~/py-env/bin/activate
