Python Tricks
=============

HTTP Server serving current directory

    python -m SimpleHTTPServer 8000
    python3 -m http.server 8080

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

bootstrapping virtualenv

    curl -O http://pypi.python.org/packages/source/v/virtualenv/virtualenv-1.8.2.tar.gz
    tar xzf virtualenv-*.tar.gz
    $(which python) virtualenv-*/virtualenv.py  --system-site-packages ~/py-env
    rm -rf virtualenv-*/
    rm -rf virtualenv-*.tar.gz
    source ~/py-env/bin/activate
