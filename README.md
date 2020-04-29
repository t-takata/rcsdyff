rcsdyff
====

rcsdiff-like tool that uses dyff instead of diff.

## Requirement
- [RCS](https://www.gnu.org/software/rcs/)
- [dyff](https://github.com/homeport/dyff)

## Usage

```
## Diff between head and working file
$ rcsdyff docker-compose.yml
     _        __  __
   _| |_   _ / _|/ _|  between /tmp/rcsdyff.3438.1.3
 / _' | | | | |_| |_       and /tmp/rcsdyff.3438.-
| (_| | |_| |  _|  _|
 \__,_|\__, |_| |_|   returned one difference
        |___/

services.httpd.image
  ± value change
    - httpd:latest
    + httpd:alpine
```

```
## Diff between specified revision and working file
$ rcsdyff -r1.2 docker-compose.yml
     _        __  __
   _| |_   _ / _|/ _|  between /tmp/rcsdyff.3480.1.2
 / _' | | | | |_| |_       and /tmp/rcsdyff.3480.-
| (_| | |_| |  _|  _|
 \__,_|\__, |_| |_|   returned one difference
        |___/

services.httpd.image
  ± value change
    - httpd:2.4.43
    + httpd:alpine
```

```
## Diff between specified revisions
$ rcsdyff -r1.1 -r1.2 docker-compose.yml
     _        __  __
   _| |_   _ / _|/ _|  between /tmp/rcsdyff.3508.1.1
 / _' | | | | |_| |_       and /tmp/rcsdyff.3508.1.2
| (_| | |_| |  _|  _|
 \__,_|\__, |_| |_|   returned one difference
        |___/

services.httpd.image
  ± value change
    - httpd:2.4.41
    + httpd:2.4.43
```

## Licence

MIT

## Author

[t-takata](https://github.com/t-takata)
