.. _Security_overview:

########
Overview
########

=================
Security Overview
=================

The |__PART_FAMILY_DEVICE_NAMES__| SoC offers a comprehensive set of 
security features that protect embedded Linux applications. This guide 
offers a starting point to understand and implement these capabilities 
as part of product development, with the following advantages:

* **Hardware-backed security** - Leverages built-in security hardware 
  for robust protection
* **Defense in-depth** - Creates many layers of security to protect 
  against various threats
* **Industry standards compliance** - Implements security features that 
  help meet regulatory requirements
* **Flexible implementation** - Allows security features that can be 
  tailored to specific application needs

================
Security Domains
================

Below is an overview of the security framework's main domains:

.. figure:: ./images/security_framework.png

These security domains create a chain of trust protecting the 
|__PART_FAMILY_DEVICE_NAMES__| SoC from boot through runtime and storage,
ensuring system integrity and data confidentiality.

=============================
Security Features at a Glance
=============================

The following table lists some of the key Security Features:

.. ifconfig:: CONFIG_part_variant in ('AM62LX')

  +-------------------------+-----------------------------------------------------------+--------------------------------------+
  | **Security Feature**    | **Description**                                           | **Links**                            |
  +=========================+===========================================================+======================================+
  | **Authenticated Boot**  | Verifies each boot component to ensure only authorized    | :ref:`auth_boot_guide`               |
  |                         | code executes on the device                               |                                      |
  +-------------------------+-----------------------------------------------------------+--------------------------------------+
  | **Crypto Acceleration** | Hardware driver support for cryptographic algorithms      | :ref:`DTHEv2-Crypto-Accelerator`     |
  +-------------------------+-----------------------------------------------------------+--------------------------------------+
  | **Key Management**      | Tools for secure key provisioning                         | :ref:`key-writer-lite-label`         |
  +-------------------------+-----------------------------------------------------------+--------------------------------------+
  | **Secure Storage**      | Protection mechanisms for sensitive data                  | :ref:`secure-storage-with-rpmb`      |
  +-------------------------+-----------------------------------------------------------+--------------------------------------+
  | **Trusted Execution**   | Implementation of secure monitor (EL3) firmware that      | :ref:`foundational-components-atf`   |
  |                         | manages the secure boot process and TrustZone transitions |                                      |
  +                         +-----------------------------------------------------------+--------------------------------------+
  |                         | Trusted Execution Environment that enables isolated       | :ref:`foundational-components-optee` |
  |                         | execution of security-sensitive applications and services |                                      |
  +-------------------------+-----------------------------------------------------------+--------------------------------------+

.. ifconfig:: CONFIG_part_variant not in ('AM62LX')

  +-------------------------+-----------------------------------------------------------+--------------------------------------+
  | Security Feature        | Description                                               | Links                                |
  +=========================+===========================================================+======================================+
  | **Authenticated Boot**  | Verifies each boot component to ensure only authorized    | :ref:`auth_boot_guide`               |
  |                         | code executes on the device                               |                                      |
  +-------------------------+-----------------------------------------------------------+--------------------------------------+
  | **Crypto Acceleration** | Hardware driver support for cryptographic algorithms      | :ref:`SAUL-Crypto-Accelerator`       |
  +-------------------------+-----------------------------------------------------------+--------------------------------------+
  | **Secure Storage**      | Protection mechanisms for sensitive data                  | :ref:`secure-storage-with-rpmb`      |
  +-------------------------+-----------------------------------------------------------+--------------------------------------+
  | **SELinux**             | Kernel security module providing policy-based access      | :ref:`selinux_guide`                 |
  |                         | control for processes, files, and system objects          |                                      |
  +-------------------------+-----------------------------------------------------------+--------------------------------------+
  | **Trusted Execution**   | Implementation of secure monitor (EL3) firmware that      | :ref:`foundational-components-atf`   |
  |                         | manages the secure boot process and TrustZone transitions |                                      |
  +                         +-----------------------------------------------------------+--------------------------------------+
  |                         | Trusted Execution Environment that enables isolated       | :ref:`foundational-components-optee` |
  |                         | execution of security-sensitive applications and services |                                      |
  +-------------------------+-----------------------------------------------------------+--------------------------------------+

