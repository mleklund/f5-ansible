.. _bigip_dns_zone:


bigip_dns_zone - Manages DNS zones on a BIG-IP
++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 2.2


.. contents::
   :local:
   :depth: 1


Synopsis
--------

This module manages DNS zones described in the iControl Management documentation


Requirements (on host that executes module)
-------------------------------------------

  * bigsuds
  * distutils


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
    <td>options<br/><div style="font-size: small;"></div></td>
    <td>no</td>
    <td></td>
        <td><ul></ul></td>
        <td><div>A sequence of options for the view</div></td></tr>
            <tr>
    <td>password<br/><div style="font-size: small;"></div></td>
    <td>yes</td>
    <td></td>
        <td><ul></ul></td>
        <td><div>BIG-IP password</div></td></tr>
            <tr>
    <td>server<br/><div style="font-size: small;"></div></td>
    <td>yes</td>
    <td></td>
        <td><ul></ul></td>
        <td><div>BIG-IP host</div></td></tr>
            <tr>
    <td>state<br/><div style="font-size: small;"></div></td>
    <td>no</td>
    <td>present</td>
        <td><ul><li>present</li><li>absent</li></ul></td>
        <td><div>Whether the record should exist.  When <code>absent</code>, removes the record.</div></td></tr>
            <tr>
    <td>user<br/><div style="font-size: small;"></div></td>
    <td>yes</td>
    <td></td>
        <td><ul></ul></td>
        <td><div>BIG-IP username</div></br>
        <div style="font-size: small;">aliases: username<div></td></tr>
            <tr>
    <td>zone<br/><div style="font-size: small;"></div></td>
    <td>yes</td>
    <td></td>
        <td><ul></ul></td>
        <td><div>The name of the zone</div></td></tr>
        </table>
    </br>



Examples
--------

 ::

    - name: Add a view, named "internal", to organization.com zone
      local_action:
          module: bigip_view
          username: 'admin'
          password: 'admin'
          hostname: 'bigip.organization.com'
          zone_names:
              - 'organization.com'
          state: 'present'
          options:
              - domain_name: elliot.organization.com
              ip_address: 10.1.1.1


Notes
-----

.. note:: Requires the bigsuds Python package on the remote host. This is as easy as pip install bigsuds
.. note:: https://devcentral.f5.com/wiki/iControl.Management__Zone.ashx


    
This is an Extras Module
------------------------

For more information on what this means please read :doc:`modules_extra`

    
For help in developing on modules, should you be so inclined, please read :doc:`community`, :doc:`developing_test_pr` and :doc:`developing_modules`.

