nfsn.py
=======

nfsn.py is an ultra simple NFSN API helper build on [requests][]. nfsn.py is
a [requests custom authentication helper][requests-auth] that implements the
NFSN [request signing protocol][nfsn-api]. Using it really simple, just
put `nfsn.py` in your current directory and then use it:

```python
import requests
from nfsn import NFSNAuth

# You can set the details globally
NFSNAuth.login = "your NFSN login"
NFSNAuth.api_key = "your NFSN api key"

session = requests.session(auth=NFSNAuth())

# or you can supply the details as constructor arguments
session = requests.session(auth=NFSNAuth("your NFSN login", "your NFSN api key"))

# Then just use requests as normal
session.post("https://api.nearlyfreespeech.net/dns/example.com/listRRs")
```

  [requests]: http://docs.python-requests.org/en/latest/index.html
  [nfsn-api]: https://members.nearlyfreespeech.net/wiki/API/Introduction
  [requests-auth]: http://docs.python-requests.org/en/latest/user/advanced/#custom-authentication
