import ReactPlayer from ‘react-player’;

Instance
========

--------------

Under the heading Instance you will find the possibility to create new
Web-GIS instances or to edit existing ones. By selecting an instance,
the edit menu opens.

.. figure:: ../../static/img/instance_overview.png
   :alt: admin-client

   admin-client

As soon as an instance entry is filled with all required information, it
can be saved via the button |Save Admin Instance|.

The |Reset Admin Instance| button can be used to reset the instance
input form.

When creating/editing an instance, the fields *Client configuration* and
*Layertree* must be filled in addition to the name for the instance.

Client configuration
--------------------

This field stores the configuration of the instance in JSON format. By
editing the JSON format parameters like the initial zoom level, the
title, or the color-scheme of the instance can be modified:

.. raw:: html

   <details>

.. raw:: html

   <summary>

Client configuration as JSON

.. raw:: html

   </summary>

.. container::

   .. raw:: html

      <pre>
        {
        JSON.stringify(
        {
         "mapView": {
          "zoom": 3,
          "center": [
            11.4717964,
            48.155004
          ],
          "extent": null,
          "projection": "EPSG:3857",
          "resolutions": [
            8920,
            4480,
            2240,
            1120,
            560,
            350,
            280,
            140,
            70,
            28,
            14,
            7,
            2.8,
            1.4,
            0.7,
            0.28,
            0.07
          ]
        },
        "description": "This is the Web GIS 1",
        "theme": {
          "primaryColor": "#555555",
          "secondaryColor": "#73b3fb",
          "complementaryColor": "#ffffff",
          "logoPath": "https://cloud.code-de.org:8080/279dbc97d5b5434fa8aeacf09c08c520:eolab_prod/static/img/eolab1.png"
        }
        }, null, '  ')
        }
        </pre>

.. raw:: html

   </details>

This is a full list of parameters that can be edited:

+-----------------+-----------------+-----------------+-----------------+
| Key             | Description     | Example         | Required        |
+=================+=================+=================+=================+
| ``ma            | Zoom level at   | 7               | false           |
| pView -> zoom`` | which the map   |                 |                 |
|                 | is initially    |                 |                 |
|                 | loaded          |                 |                 |
+-----------------+-----------------+-----------------+-----------------+
| ``mapV          | Center of the   | “center”:       | true            |
| iew -> center`` | map to which    | [7,51]          |                 |
|                 | the map is      |                 |                 |
|                 | initially       |                 |                 |
|                 | zoomed          |                 |                 |
+-----------------+-----------------+-----------------+-----------------+
| ``mapV          | The maximum     | ‘[2.56          | false           |
| iew -> extent`` | extent of the   | 83045738288137, |                 |
|                 | map (in WGS84)  | 45.4            |                 |
|                 |                 | 29089001638076, |                 |
|                 |                 | 19.3            |                 |
|                 |                 | 82621082401887, |                 |
|                 |                 | 57.28           |                 |
|                 |                 | 3993958205926]’ |                 |
+-----------------+-----------------+-----------------+-----------------+
| ``mapView       | Projection of   | ‘EPSG:25832’    | false           |
| -> projection`` | the map         |                 |                 |
+-----------------+-----------------+-----------------+-----------------+
| ``mapView -     | The list of     | ‘[2445          | false           |
| > resolutions`` | resolutions of  | .9849047851562, |                 |
|                 | the map         | 1222            |                 |
|                 |                 | .9924523925781, |                 |
|                 |                 | 611.            |                 |
|                 |                 | 4962261962891]’ |                 |
+-----------------+-----------------+-----------------+-----------------+
| ``description`` | Description of  | ‘My Web-GIS’    | false           |
|                 | the instance to |                 |                 |
|                 | be displayed on |                 |                 |
|                 | the start page  |                 |                 |
+-----------------+-----------------+-----------------+-----------------+
| ``theme ->      | Defines the     | ‘#444444’       | false           |
|  primaryColor`` | background      |                 |                 |
|                 | color of the    |                 |                 |
|                 | header and      |                 |                 |
|                 | footer element  |                 |                 |
+-----------------+-----------------+-----------------+-----------------+
| ``theme -> s    | Defines the     | ‘#ffc0cb’       | false           |
| econdaryColor`` | hovering color  |                 |                 |
|                 | of text         |                 |                 |
|                 | elements and    |                 |                 |
|                 | buttons         |                 |                 |
+-----------------+-----------------+-----------------+-----------------+
| `               | Defines the     | ‘#000000’       | false           |
| `theme -> compl | font color of   |                 |                 |
| ementaryColor`` | text elements   |                 |                 |
|                 | within header   |                 |                 |
|                 | and footer      |                 |                 |
|                 | component       |                 |                 |
+-----------------+-----------------+-----------------+-----------------+
| ``them          | URL to logo     | http            | false           |
| e -> logoPath`` | which is shown  | s://my-logo.de/ |                 |
|                 | in header       | img/my-logo.png |                 |
|                 | component       |                 |                 |
+-----------------+-----------------+-----------------+-----------------+

You can find an illustrative example of how to change the zoom level,
the center and the primary color in the following video:

Layertree
---------

This field stores the configuration for the instance’s layertree in JSON
format:

.. raw:: html

   <details>

.. raw:: html

   <summary>

Layertree configuration as JSON

.. raw:: html

   </summary>

.. container::

   .. raw:: html

      <pre>
        {
        JSON.stringify(
        {
        "title": "root",
        "children": [
          {
            "title": "Copernicus Services",
            "checked": false,
            "children": [
              {
                "title": "Land - VHR Mosaic",
                "checked": false,
                "children": [
                  {
                    "title": "VHR 2018",
                    "checked": false,
                    "layerId": 23
                  },
                  {
                    "title": "VHR 2012",
                    "checked": false,
                    "layerId": 22
                  }
                ]
              },
              {
                "title": "Surfaceobservation - ESA WorldCover",
                "checked": false,
                "children": [
                  {
                    "title": "Worldcover 2020",
                    "checked": false,
                    "layerId": 26
                  }
                ]
              }
            ]
          },
          {
            "title": "Community Contributions",
            "checked": true,
            "children": [
              {
                "title": "Incora",
                "checked": true,
                "children": [
                  {
                    "title": "Land Cover 2016",
                    "checked": false,
                    "layerId": 19
                  },
                  {
                    "title": "Land Cover 2019",
                    "checked": false,
                    "layerId": 20
                  },
                  {
                    "title": "Land Cover 2020",
                    "checked": true,
                    "layerId": 21
                  }
                ]
              },
              {
                "title": "Building Heigt Map (DE)",
                "checked": false,
                "layerId": 27
              },
              {
                "title": "Land Cover Fraction Map (DE)",
                "checked": false,
                "layerId": 25
              }
            ]
          },
          {
            "title": "Backgroundlayer",
            "checked": true,
            "children": [
              {
                "title": "GEBCO",
                "checked": false,
                "layerId": 28
              },
              {
                "title": "OSM-WMS",
                "checked": false,
                "layerId": 24
              },
              {
                "title": "OSM-WMS (gray)",
                "checked": true,
                "layerId": 16
              }
            ]
          }
        ]
        }, null, '  ')
        }
        </pre>

.. raw:: html

   </details>

The layertree consists of two different elements ``Layer`` and
``Layergroup`` which are defined in the JSON document. A ``Layer`` has
the following structure:

::

   "title": "My Layer",
   "checked": false,
   "layerId": 42

One or more layers can be part of a ``Layergroup``. In this case they
need to be added to the ``children``-array as follow:

::

   "title": "My Layergroup",
   "checked": true,
   "children": [
     {
       "title": "Layer 1",
       "checked": true,
       "layerId": 12
     },
     {
       "title": "Layer 2",
       "checked": true,
       "layerId": 24
     },
     {
       "title": "Layer 3",
       "checked": true,
       "layerId": 16
     }
   ]

Also a ``Layergroup`` can be part of the ``children``-array. In that
case just another hierarchy level will be added.

.. caution::

   The layerId has to be corresponding to the *Subjects*-layerId!

This is a full list of parameters that can be edited:

+-----------------+-----------------+-----------------+-----------------+
| Key             | Description     | Example         | Required        |
+=================+=================+=================+=================+
| ``title``       | Layer- or       | ‘My base        | false           |
|                 | Groupname       | layers’         |                 |
|                 | displayed       |                 |                 |
|                 | within the      |                 |                 |
|                 | layertree. If   |                 |                 |
|                 | not set, the    |                 |                 |
|                 | layername of    |                 |                 |
|                 | the internal    |                 |                 |
|                 | geoserver will  |                 |                 |
|                 | be used         |                 |                 |
+-----------------+-----------------+-----------------+-----------------+
| ``checked``     | Defines whether | true            | false           |
|                 | a layer or all  |                 |                 |
|                 | layers within a |                 |                 |
|                 | layergroup      |                 |                 |
|                 | shall be        |                 |                 |
|                 | visible         |                 |                 |
|                 | initially       |                 |                 |
+-----------------+-----------------+-----------------+-----------------+
| ``children``    | Array of layer  | [{“title”:      | false           |
|                 | and layergroup  | “layer 1”,      |                 |
|                 |                 | “checked”:      |                 |
|                 |                 | true,           |                 |
|                 |                 | “layerId”:1 }]  |                 |
+-----------------+-----------------+-----------------+-----------------+
| ``layerId``     | LayerId         | 1               | true            |
|                 | corresponding   |                 |                 |
|                 | to the LayerId  |                 |                 |
|                 | of the          |                 |                 |
|                 | `Subject <../   |                 |                 |
|                 | admin-client/02 |                 |                 |
|                 | -subject.md>`__ |                 |                 |
+-----------------+-----------------+-----------------+-----------------+

You can find an illustrative example of how to change the name or
initial visibility of a layer in the following video:

Layer configuration
-------------------

Within the layer configuration window, predefined layer settings from
the `Subjects <../admin-client/02-subject.md>`__ section can be
overwritten and customized for the particular instance.

Each layer to be modified is an object within a array:

::

   [
     {
       "layerId": 1,
       "clientConfig": {
         "opacity": 0.5
       }
     },
     {
       "layerId": 2,
       "clientConfig": {
         "hoverable": true
       }
     },
     {
       "layerId": 3,
       "sourceConfig": {
         "useBearerToken": true
       }
     }
   ]

This is a full list of parameters that can be edited:

+-----------------+-----------------+-----------------+-----------------+
| Key             | Description     | Example         | Required        |
+=================+=================+=================+=================+
| ``layerId``     | LayerId         | 1               | true            |
|                 | corresponding   |                 |                 |
|                 | to the LayerId  |                 |                 |
|                 | of the          |                 |                 |
|                 | `Subject <../   |                 |                 |
|                 | admin-client/02 |                 |                 |
|                 | -subject.md>`__ |                 |                 |
+-----------------+-----------------+-----------------+-----------------+
| ``clientConfig  | see `Client     |                 |                 |
|  -> hoverable`` | Con             |                 |                 |
|                 | figuration <../ |                 |                 |
|                 | admin-client/02 |                 |                 |
|                 | -subject.md>`__ |                 |                 |
+-----------------+-----------------+-----------------+-----------------+
| ``c             | see `Client     |                 |                 |
| lientConfig ->  | Con             |                 |                 |
| maxResolution`` | figuration <../ |                 |                 |
|                 | admin-client/02 |                 |                 |
|                 | -subject.md>`__ |                 |                 |
+-----------------+-----------------+-----------------+-----------------+
| ``c             | see `Client     |                 |                 |
| lientConfig ->  | Con             |                 |                 |
| minResolution`` | figuration <../ |                 |                 |
|                 | admin-client/02 |                 |                 |
|                 | -subject.md>`__ |                 |                 |
+-----------------+-----------------+-----------------+-----------------+
| ``clientConf    | see `Client     |                 |                 |
| ig -> opacity`` | Con             |                 |                 |
|                 | figuration <../ |                 |                 |
|                 | admin-client/02 |                 |                 |
|                 | -subject.md>`__ |                 |                 |
+-----------------+-----------------+-----------------+-----------------+
| ``cl            | see `Client     |                 |                 |
| ientConfig -> p | Con             |                 |                 |
| ropertyConfig`` | figuration <../ |                 |                 |
|                 | admin-client/02 |                 |                 |
|                 | -subject.md>`__ |                 |                 |
+-----------------+-----------------+-----------------+-----------------+
| ``clientConfig  | see `Client     |                 |                 |
| -> searchable`` | Con             |                 |                 |
|                 | figuration <../ |                 |                 |
|                 | admin-client/02 |                 |                 |
|                 | -subject.md>`__ |                 |                 |
+-----------------+-----------------+-----------------+-----------------+
| ``              | see `Client     |                 |                 |
| clientConfig -> | Con             |                 |                 |
|  searchConfig`` | figuration <../ |                 |                 |
|                 | admin-client/02 |                 |                 |
|                 | -subject.md>`__ |                 |                 |
+-----------------+-----------------+-----------------+-----------------+
| ``s             | see `Source     |                 |                 |
| ourceConfig ->  | Con             |                 |                 |
| requestParams`` | figuration <../ |                 |                 |
|                 | admin-client/02 |                 |                 |
|                 | -subject.md>`__ |                 |                 |
+-----------------+-----------------+-----------------+-----------------+
| `               | see `Source     |                 |                 |
| `sourceConfig - | Con             |                 |                 |
| > resolutions`` | figuration <../ |                 |                 |
|                 | admin-client/02 |                 |                 |
|                 | -subject.md>`__ |                 |                 |
+-----------------+-----------------+-----------------+-----------------+
| ``sourceConfig  | see `Source     |                 |                 |
| -> tileOrigin`` | Con             |                 |                 |
|                 | figuration <../ |                 |                 |
|                 | admin-client/02 |                 |                 |
|                 | -subject.md>`__ |                 |                 |
+-----------------+-----------------+-----------------+-----------------+
| ``sourceConfi   | see `Source     |                 |                 |
| g -> tileSize`` | Con             |                 |                 |
|                 | figuration <../ |                 |                 |
|                 | admin-client/02 |                 |                 |
|                 | -subject.md>`__ |                 |                 |
+-----------------+-----------------+-----------------+-----------------+
| ``source        | see `Source     |                 |                 |
| Config -> url`` | Con             |                 |                 |
|                 | figuration <../ |                 |                 |
|                 | admin-client/02 |                 |                 |
|                 | -subject.md>`__ |                 |                 |
+-----------------+-----------------+-----------------+-----------------+
| ``so            | see `Source     |                 |                 |
| urceConfig -> u | Con             |                 |                 |
| seBearerToken`` | figuration <../ |                 |                 |
|                 | admin-client/02 |                 |                 |
|                 | -subject.md>`__ |                 |                 |
+-----------------+-----------------+-----------------+-----------------+

Configure Tools
---------------

This field stores the configuration for the instance tools in JSON
format:

.. raw:: html

   <details>

.. raw:: html

   <summary>

Tool configuration as JSON

.. raw:: html

   </summary>

.. container::

   .. raw:: html

      <pre>
        {
        JSON.stringify(
        [
        {
          "name": "measure_tools",
          "config": {
            "visible": true
          }
        },
        {
          "name": "measure_tools_distance",
          "config": {
            "visible": true
          }
        },
        {
          "name": "measure_tools_area",
          "config": {
            "visible": true
          }
        },
        {
          "name": "draw_tools",
          "config": {
            "visible": true
          }
        },
        {
          "name": "draw_tools_point",
          "config": {
            "visible": true
          }
        },
        {
          "name": "draw_tools_line",
          "config": {
            "visible": true
          }
        },
        {
          "name": "draw_tools_polygon",
          "config": {
            "visible": true
          }
        },
        {
          "name": "draw_tools_circle",
          "config": {
            "visible": true
          }
        },
        {
          "name": "draw_tools_rectangle",
          "config": {
            "visible": true
          }
        },
        {
          "name": "draw_tools_annotation",
          "config": {
            "visible": true
          }
        },
        {
          "name": "draw_tools_modify",
          "config": {
            "visible": true
          }
        },
        {
          "name": "draw_tools_upload",
          "config": {
            "visible": true
          }
        },
        {
          "name": "draw_tools_download",
          "config": {
            "visible": true
          }
        },
        {
          "name": "draw_tools_delete",
          "config": {
            "visible": true
          }
        },
        {
          "name": "feature_info",
          "config": {
            "visible": true
          }
        },
        {
          "name": "print",
          "config": {
            "visible": true
          }
        },
        {
          "name": "tree",
          "config": {
            "visible": true
          }
        },
        {
          "name": "permalink",
          "config": {
            "visible": true
          }
        },
        {
          "name": "language_selector",
          "config": {
            "visible": true
          }
        }
        ], null, '  ')
        }
        </pre>

.. raw:: html

   </details>

Every available tool from the toolbox is recorded in this document. By
changing the visibility of a certain tool, the tool will be availiable
within the Web-GIS instance or not, depending on the value.

This is a full list of parameters that can be edited:

+-----------------------------------+-----------------------------------+
| Key                               | Description                       |
+===================================+===================================+
| ``name``                          | Name of the tool. This parameter  |
|                                   | should not be edited              |
+-----------------------------------+-----------------------------------+
| ``config -> visible``             | Sets the visibility of a certain  |
|                                   | tool within the Web-GIS instance  |
+-----------------------------------+-----------------------------------+

.. container:: info

   If you leave the configuration blank, all tools will be availiable
   per default. Once one tool is mentioned, all unmentioned tools will
   remain unavailable.

You can find an illustrative example of how to change the visibility of
a tool in the following video:

User permissions
----------------

In the user permission field, users can be activated for the specific
instances and assigned user permissions.

.. figure:: ../../static/img/user_permissions.png
   :alt: user_permissions

   user_permissions

Clicking on the |admin-client| button opens a new window with two input
fields:

.. figure:: ../../static/img/add_permission.png
   :alt: add_permissions

   add_permissions

After entering the e-mail address of a user, various permissions can be
assigned for that specific user. The following permissions are
availiable:

+-----------------------------------+-----------------------------------+
| Key                               | Description                       |
+===================================+===================================+
| ``Read``                          | If corresponding to the users     |
|                                   | role, the user can read the       |
|                                   | JSON-files configuring the        |
|                                   | Web-GIS                           |
+-----------------------------------+-----------------------------------+
| ``Update``                        | If corresponding to the users     |
|                                   | role, the user can modify the     |
|                                   | JSON-files configuring the        |
|                                   | Web-GIS                           |
+-----------------------------------+-----------------------------------+
| ``Update & Delete``               | If corresponding to the users     |
|                                   | role, the user can modify and     |
|                                   | delete the JSON-files configuring |
|                                   | the Web-GIS                       |
+-----------------------------------+-----------------------------------+
| ``Owner``                         | If corresponding to the users     |
|                                   | role, the user can modify and     |
|                                   | delete the JSON-files configuring |
|                                   | the Web-GIS and grant permissions |
|                                   | to new users                      |
+-----------------------------------+-----------------------------------+

.. container:: info

   Every user listed within the permission grid has access to the
   Web-GIS instance. The permissions granted only affect users who also
   have the ``admin`` role, as only these users can access the admin
   client and thus modify the configurations.

You can find an illustrative example of how to grant permissions to a
user in the following video:

.. |Save Admin Instance| image:: ../../static/img/save_instance.png
.. |Reset Admin Instance| image:: ../../static/img/reset_instance.png
.. |admin-client| image:: ../../static/img/plus.png
