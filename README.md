NGSI source operator
====================

The NGSI source operator is a WireCloud operator usable for adding
NGSI subscription support to your dashboards in a simple way. Those
subscriptions are a great feature provided by the [Orion Context
Broker](http://catalogue.fiware.org/enablers/publishsubscribe-context-broker-orion-context-broker).

Latest version of this operator is always [provided in FIWARE
Lab](https://store.lab.fi-ware.org/search/keyword/OrionStarterKit) where you
can make use of it on the [Mashup portal](https://mashup.lab.fi-ware.org).
Remember to take a look into the example mashups provided in the OrionStarterKit offering.

Build
-----

Be sure to have installed [Node.js](http://node.js). For example, you can install it on Ubuntu and Debian running the following commands:

```bash
curl -sL https://deb.nodesource.com/setup | sudo bash -
sudo apt-get install nodejs
sudo apt-get install npm
```

Install other npm dependencies by running:

```bash
npm install
```

For build the widget you need download grunt:

```bash
sudo npm install -g grunt-cli
```

And now, you can use grunt:

```bash
grunt
```

If everything goes well, you will find a wgt file in the `dist` folder.

Settings and Usage
------------------

### Settings

- **NGSI server URL:** URL of the Orion Context Broker to use for retrieving
  entity information.
- **Use the FIWARE credentials of the user:** Use the FIWARE credentials of the
  user logged into WireCloud. Take into account this option cannot be enabled if
  you want to use this widget in a public workspace as anonoymous users doesn't
  have a valid FIWARE auth token. As an alternative, you can make use of the
  "Use the FIWARE credentials of the workspace owner" preference.
- **Use the FIWARE credentials of the dashboard owner**: Use the FIWARE
  credentials of the owner of the workspace. This preference takes preference
  over "Use the FIWARE credentials of the user". This feature is available on
  WireCloud 0.7.0+ in a experimental basis, future versions of WireCloud can
  change the way to use it making this option not funcional and requiring you to
  upgrade this operator.
- **NGSI entity types:** A comma separated list of entity types to use for
  filtering entities from the Orion Context broker. This field cannot be empty.
- **Id pattern:** Id pattern for filtering entities. This preference can be
  empty, in that case, entities won't be filtered by id.

### Wiring

##### Input Endpoints

* This widget has no input endpoint

##### Output Endpoints

*   **Provide entity:** This operator sends an event thought this endpoint for
    each entity update retrieved from the context broker. In addition to this, this
    operator send an event for every entity available initially on the context
    broker.

    In any case, event data follows the format used by the NGSI API of WireCloud
    for returning. E.g.

    ```json
    {
        "id": "van4",
        "type": "Van",
        "current_position": "43.47173, -3.7967205"
    }
    ```

Copyright and License
---------------------

Copyright (c) 2014-2015 CoNWeT Lab., Universidad Politecnica de Madrid

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

  http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
