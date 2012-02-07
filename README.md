Thrift Python Software Library
==============================

This is a patched version of thrift 0.8.0 with the unicode patches applied.
For some reason (yet not known to me) the unicode handling patches from 0.4.0
are not present in 0.8.0 anymore, therefore inserting strings with unicode
characters might result in a UnicodeEncodeError in fastbinary.

See https://issues.apache.org/jira/browse/THRIFT-1460 for more info and updates
on this.

The `patches/` directory contains all patches applied. Note that some patches
include some python code generator patches. The code generator is not in the
thrift pypi package and therefore these patches have not been applied.

Inserting UTF8 Strings into cassandra works now. YEEEHA :-)

-- originell


License
-------

Licensed to the Apache Software Foundation (ASF) under one
or more contributor license agreements. See the NOTICE file
distributed with this work for additional information
regarding copyright ownership. The ASF licenses this file
to you under the Apache License, Version 2.0 (the
"License"); you may not use this file except in compliance
with the License. You may obtain a copy of the License at

  http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing,
software distributed under the License is distributed on an
"AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
KIND, either express or implied. See the License for the
specific language governing permissions and limitations
under the License.

Using Thrift with Python
------------------------

Thrift is provided as a set of Python packages. The top level package is
thrift, and there are subpackages for the protocol, transport, and server
code. Each package contains modules using standard Thrift naming conventions
(i.e. TProtocol, TTransport) and implementations in corresponding modules
(i.e. TSocket).  There is also a subpackage reflection, which contains
the generated code for the reflection structures.

The Python libraries can be installed manually using the provided setup.py
file, or automatically using the install hook provided via autoconf/automake.
To use the latter, become superuser and do make install.
