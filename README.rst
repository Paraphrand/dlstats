Widukind - dlstats
==================

|Build Status| |Build Doc| |Coveralls|

**Fetchers for the `DB.nomics project <https://db.nomics.world/>`_**

**`DB.nomics <https://db.nomics.world/>`_ is a database of international macroeconomic data collected on public web servers of statistical offices worldwide.**

*Please ask your questions to the `DB.nomics forum <https://forum.db.nomics.world/>`_.*

Requires
--------

- MongoDB 3+
- Python 3.4
- `Widukind Common`_
- `Widukind Web`_ for WebUI (Optional)
- `Widukind Api`_ Rest API (Optional)

Installation with Python
------------------------

See Dockerfile for installation example.

Installation with Docker
------------------------

Use `Widukind Docker`_ project with docker-compose or manual installation:

**Requires:**

* Docker 1.9+
* docker-compose 1.5+
* sudo right or root access

::

    docker run -d --name mongodb mongo \
      mongod --bind_ip 0.0.0.0 --smallfiles --noauth --directoryperdb

    git clone https://git.nomics.world/dbnomics/dlstats.git

    cd dlstats

    docker build -t widukind/cli .

    docker run -it --rm --link mongodb:mongodb \
      -e WIDUKIND_MONGODB_URL=mongodb://mongodb/widukind \
      widukind/cli dlstats --help

    # Tips: run dlstats client with alias
    alias dlstats="docker run -it --rm --link mongodb:mongodb -e WIDUKIND_MONGODB_URL=mongodb://mongodb/widukind widukind/cli dlstats"
    dlstats --help


.. |Build Status| image:: https://travis-ci.org/Widukind/dlstats.svg?branch=master
   :target: https://travis-ci.org/Widukind/dlstats
   :alt: Travis Build Status

.. |Build Doc| image:: https://readthedocs.org/projects/widukind-dlstats/badge/?version=latest
   :target: http://widukind-dlstats.readthedocs.org/en/latest/?badge=latest
   :alt: Documentation Status

.. |Coveralls| image:: https://coveralls.io/repos/Widukind/dlstats/badge.svg?branch=master&service=github
   :target: https://coveralls.io/github/Widukind/dlstats?branch=master
   :alt: Coverage


LICENSE
-------

GNU Affero General Public License version 3


.. _`Widukind Web`: https://git.nomics.world/dbnomics/widukind-web
.. _`Widukind Api`: https://git.nomics.world/dbnomics/widukind-api
.. _`Widukind Docker`: https://git.nomics.world/dbnomics/widukind-docker
.. _`Widukind Common`: https://git.nomics.world/dbnomics/widukind-common
