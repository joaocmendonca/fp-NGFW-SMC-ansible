.. _bgp_element_facts:


bgp_element_facts - Facts about BGP based elements in the SMC
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++


.. contents::
   :local:
   :depth: 2


Synopsis
--------


* BGP elements are the building blocks to building a BGP configuration on a firewall. Use this module to obtain available elements and their values.



Requirements (on host that executes module)
-------------------------------------------

  * smc-python


Options
-------

.. raw:: html

    <table border=1 cellpadding=4>

    <tr>
    <th class="head">parameter</th>
    <th class="head">required</th>
    <th class="head">default</th>
    <th class="head">choices</th>
    <th class="head">comments</th>
    </tr>

    <tr>
    <td>case_sensitive<br/><div style="font-size: small;"></div></td>
    <td>no</td>
    <td>True</td>
    <td></td>
	<td>
        <p>Whether to do a case sensitive match on the filter specified</p>
	</td>
	</tr>
    </td>
    </tr>

    <tr>
    <td>element<br/><div style="font-size: small;"></div></td>
    <td>yes</td>
    <td></td>
    <td><ul><li>ip_access_list</li><li>ip_prefix_list</li><li>ipv6_access_list</li><li>ipv6_prefix_list</li><li>as_path_access_list</li><li>community_access_list</li><li>extended_community_access_list</li><li>external_bgp_peer</li><li>bgp_peering</li><li>autonomous_system</li></ul></td>
	<td>
        <p>Type of bgp element to retrieve</p>
	</td>
	</tr>
    </td>
    </tr>

    <tr>
    <td>exact_match<br/><div style="font-size: small;"></div></td>
    <td>no</td>
    <td></td>
    <td></td>
	<td>
        <p>Whether to do an exact match on the filter specified</p>
	</td>
	</tr>
    </td>
    </tr>

    <tr>
    <td>filter<br/><div style="font-size: small;"></div></td>
    <td>no</td>
    <td>*</td>
    <td></td>
	<td>
        <p>String value to match against when making query. Matches all if not specified. A filter will attempt to find a match in the name, primary key field or comment field of a given record.</p>
	</td>
	</tr>
    </td>
    </tr>

    <tr>
    <td>limit<br/><div style="font-size: small;"></div></td>
    <td>no</td>
    <td>10</td>
    <td></td>
	<td>
        <p>Limit the number of results. Set to 0 to remove limit.</p>
	</td>
	</tr>
    </td>
    </tr>

    <tr>
    <td>smc_address<br/><div style="font-size: small;"></div></td>
    <td>no</td>
    <td></td>
    <td></td>
	<td>
        <p>FQDN with port of SMC. The default value is the environment variable <code>SMC_ADDRESS</code></p>
	</td>
	</tr>
    </td>
    </tr>

    <tr>
    <td>smc_alt_filepath<br/><div style="font-size: small;"></div></td>
    <td>no</td>
    <td></td>
    <td></td>
	<td>
        <p>Provide an alternate path location to read the credentials from. File is expected to be stored in ~.smcrc. If provided, address and api_key settings are not required and will be ignored.</p>
	</td>
	</tr>
    </td>
    </tr>

    <tr>
    <td>smc_api_key<br/><div style="font-size: small;"></div></td>
    <td>no</td>
    <td></td>
    <td></td>
	<td>
        <p>API key for api client. The default value is the environment variable <code>SMC_API_KEY</code> Required if the <em>address</em> parameter is defined</p>
	</td>
	</tr>
    </td>
    </tr>

    <tr>
    <td>smc_api_version<br/><div style="font-size: small;"></div></td>
    <td>no</td>
    <td></td>
    <td></td>
	<td>
        <p>Optional SMC API version to connect to. If none is provided, the latest long-term support (LTS) version of the SMC API will be used based on the SMC version. Can be set though the environment variable <code>SMC_API_VERSION</code></p>
	</td>
	</tr>
    </td>
    </tr>

    <tr>
    <td>smc_domain<br/><div style="font-size: small;"></div></td>
    <td>no</td>
    <td></td>
    <td></td>
	<td>
        <p>Optional administrative domain in the SMC to log on to. If no domain is provided, 'Shared Domain' is used. Can be set through the environment variable <code>SMC_DOMAIN</code></p>
	</td>
	</tr>
    </td>
    </tr>
    <tr>
    <td rowspan="2">smc_extra_args<br/><div style="font-size: small;"></div></td>
    <td>no</td>
    <td></td>
    <td></td>
    <td>
        <div>Extra arguments to pass to the login constructor. These arguments are generally only used if specifically requested by support personnel.</div>
    </tr>

    <tr>
    <td colspan="5">
        <table border=1 cellpadding=4>
        <caption><b>Dictionary object smc_extra_args</b></caption>

        <tr>
        <th class="head">parameter</th>
        <th class="head">required</th>
        <th class="head">default</th>
        <th class="head">choices</th>
        <th class="head">comments</th>
        </tr>

        <tr>
        <td>verify<br/><div style="font-size: small;"></div></td>
        <td>no</td>
        <td>True</td>
        <td><ul><li>yes</li><li>no</li></ul></td>
        <td>
            <div>If the connection to the SMC API is HTTPS, you can set this to True, or provide a path to a client certificate to verify the SMC SSL certificate. You can also explicitly set this to False.</div>
        </td>
        </tr>

        </table>

    </td>
    </tr>
    </td>
    </tr>
    <tr>
    <td rowspan="2">smc_logging<br/><div style="font-size: small;"></div></td>
    <td>no</td>
    <td></td>
    <td></td>
    <td>
        <div>Optionally enable SMC API logging to a file</div>
    </tr>

    <tr>
    <td colspan="5">
        <table border=1 cellpadding=4>
        <caption><b>Dictionary object smc_logging</b></caption>

        <tr>
        <th class="head">parameter</th>
        <th class="head">required</th>
        <th class="head">default</th>
        <th class="head">choices</th>
        <th class="head">comments</th>
        </tr>

        <tr>
        <td>path<br/><div style="font-size: small;"></div></td>
        <td>yes</td>
        <td></td>
        <td></td>
        <td>
            <div>Full path to the log file</div>
        </td>
        </tr>

        <tr>
        <td>level<br/><div style="font-size: small;"></div></td>
        <td>no</td>
        <td></td>
        <td></td>
        <td>
            <div>Log level as specified by the standard python logging library, in int format. Default setting is logging.DEBUG.</div>
        </td>
        </tr>

        </table>

    </td>
    </tr>
    </td>
    </tr>

    <tr>
    <td>smc_timeout<br/><div style="font-size: small;"></div></td>
    <td>no</td>
    <td></td>
    <td></td>
	<td>
        <p>Optional timeout for connections to the SMC API. Can be set through the environment variable <code>SMC_TIMEOUT</code></p>
	</td>
	</tr>
    </td>
    </tr>

    </table>
    </br>

Examples
--------

.. code-block:: yaml

    
    - name: BGP Facts
      hosts: localhost
      gather_facts: no
      tasks:
      - name: Retrieve all data about ane external bgp peer
        bgp_facts:
          element: external_bgp_peer
          filter: externalpeer

    - name: BGP Facts
      hosts: localhost
      gather_facts: no
      tasks:
      - name: Return all data about specified autonomous system
        bgp_facts:
          element: autonomous_system
          filter: remoteas
     
    - name: Routing facts about an engine
      hosts: localhost
      gather_facts: no
      tasks:
      - name: Find details about specific profile
        bgp_facts:
          element: bgp_profile
          filter: Default BGP Profile
          case_sensitive: no


Return Values
-------------

Return values that are common to all modules are documented in `Return Values <http://docs.ansible.com/ansible/latest/common_return_values.html>`_. The following fields are unique to this module:

.. raw:: html

    <table border=1 cellpadding=4>

    <tr>
    <th class="head">name</th>
    <th class="head">description</th>
    <th class="head">returned</th>
    <th class="head">type</th>
    <th class="head">sample</th>
    </tr>

    <tr>
    <td>elements</td>
    <td>
        <div>Details about BGP Peering profile</div>
    </td>
    <td align=center>always</td>
    <td align=center>list</td>
    <td align=center>[{'comment': None, 'default_originate': False, 'send_community': 'no', 'connection_profile': {'session_hold_timer': 180, 'connect_retry': 120, 'session_keep_alive': 60, 'name': 'Default BGP Connection Profile', 'type': 'bgp_connection_profile'}, 'orf_option': 'disabled', 'route_reflector_client': False, 'next_hop_self': True, 'max_prefix_option': 'not_enabled', 'remove_private_as': False, 'connected_check': 'disabled', 'read_only': False, 'soft_reconfiguration': True, 'name': 'mypeering', 'override_capability': False, 'local_as_option': 'not_set', 'system': False, 'ttl_option': 'disabled', 'type': 'bgp_peering', 'dont_capability_negotiate': False}]</td>
    </tr>
    </table>
    </br></br>


Notes
-----

.. note::
    - If a filter is not used in the query, this will return all results for the element type specified. The return data in this case will only contain the metadata for the element which will be name and type. To get detailed information about an element, use a filter. When using filters on network or service elements, the filter value will search the element fields, for example, you could use a filter of '1.1.1.1' when searching for hosts and all hosts with this IP will be returned. The same applies for services. If you are unsure of the service name but know the port you require, your filter can be by port.


Author
~~~~~~

    * Forcepoint




Status
~~~~~~

This module is flagged as **preview** which means that it is not guaranteed to have a backwards compatible interface.


