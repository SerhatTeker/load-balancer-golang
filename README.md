[![License](https://img.shields.io/badge/License-BSD%203--Clause-blue.svg)](https://opensource.org/licenses/BSD-3-Clause)

# Load Balancer
A simple TCP reverse proxy and load balancer written in Golang.

## Getting Started
This app gets requests from `localhost` on port `8080` and sends to `5000`, `5001`
and `5002` ports and get back the relative data.

### Prerequisites
1. Golang
2. Python3 or Node.js and `npx`

### Installing
Clone the repo with `ssh:`

```bash
$ git clone git@github.com:SerhatTeker/load-balancer-golang.git
```

or with `https:`

```bash
$ git clone https://github.com/SerhatTeker/load-balancer-golang.git
```

## Usage
1. Run the program:

  ```bash
  $ go run main.go
  ```

2. Run local backend servers to proxy:

  with python:

  ```bash
  $ python3 -m http.server 5000 --bind 127.0.0.1
  $ python3 -m http.server 5001 --bind 127.0.0.1
  $ python3 -m http.server 5002 --bind 127.0.0.1
  ```

  or with npx:

  ```bash
  $ npx http-server -p 5000
  $ npx http-server -p 5001
  $ npx http-server -p 5002
  ```

3. Send request to host:

  ```bash
  $ curl localhost:8080
  ```

4. See the results:

     The response:

    ```
    <!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">
    <html>
    <head>
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
    <title>Directory listing for /</title>
    </head>
    <body>
    <h1>Directory listing for /</h1>
    <hr>
    <ul>
    <li><a href=".editorconfig">.editorconfig</a></li>
    <li><a href=".git/">.git/</a></li>
    <li><a href=".gitignore">.gitignore</a></li>
    <li><a href="LICENSE">LICENSE</a></li>
    <li><a href="main.go">main.go</a></li>
    <li><a href="README.md">README.md</a></li>
    </ul>
    <hr>
    </body>
    </html>
    ```

    The app output:

    ```
    counter=1 backend=localhost:5000
    counter=2 backend=localhost:5001
    counter=3 backend=localhost:5002
    counter=4 backend=localhost:5000
    ```

## Authors
* [Serhat Teker](https://github.com/serhatteker)


## Code of Conduct
This repo uses same code as [Django Code of Conduct](https://www.djangoproject.com/conduct/) based on the [Open Code of Conduct](https://github.com/todogroup/opencodeofconduct).


## License
This work is licensed under a BSD 3-Clause "New" or "Revised" License. See the
[LICENSE](./LICENSE) for details.


## Acknowledgments
* Derived from [Ahmet Alp Balkan](https://github.com/ahmetb)'s video.
