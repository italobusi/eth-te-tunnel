---
title: "A YANG Data Model for Client-layer Tunnel"
abbrev: "Client Tunnel YANG Model"
category: std

docname: draft-zheng-ccamp-client-tunnel-yang-latest
submissiontype: IETF  # also: "independent", "editorial", "IAB", or "IRTF"
number:
date:
consensus: true
v: 3
area: "Routing"
workgroup: "Common Control and Measurement Plane"
keyword:
 - next generation
 - unicorn
 - sparkling distributed ledger
venue:
  group: "Common Control and Measurement Plane"
  type: "Working Group"
  mail: "ccamp@ietf.org"
  arch: "https://mailarchive.ietf.org/arch/browse/ccamp/"
  github: "italobusi/eth-te-tunnel"
  latest: "https://italobusi.github.io/eth-te-tunnel/draft-zheng-ccamp-client-tunnel-yang.html"

author:
  -
    name: Chaode Yu
    org: Huawei Technologies
    email: yuchaode@huawei.com
  -
    name: Haomian Zheng
    org: Huawei Technologies
    street: H1, Huawei Xiliu Beipo Village, Songshan Lake
    city: Dongguan
    region: Guangdong
    code: 523808
    country: China
    email: zhenghaomian@huawei.com
  -
    name: Aihua Guo
    org: Futurewei
    email: aihuaguo@futurewei.com
  -
    name: Italo Busi
    org: Huawei Technologies
    email: italo.busi@huawei.com
  -
    name: Yunbin Xu
    org: CAICT
    email: xuyunbin@caict.ac.cn
  -
    name: Yang Zhao
    org: China Mobile
    email: zhaoyangyjy@chinamobile.com
  -
    name: Xufeng Liu
    org: Alef Edge
    email: xufeng.liu.ietf@gmail.com

contributor:
  -
    name: Zhe Liu
    org: Huawei Technologies
    email: liuzhe123@huawei.com
  -
    name: Sergio Belotti
    org: Nokia
    email: sergio.belotti@nokia.com
  -
    name: Yingxi Yao
    org: Shanghai Bell
    email: yingxi.yao@nokia-sbell.com
  -
    name: Giuseppe Fioccola
    org: Huawei Technologies
    email: giuseppe.fioccola@huawei.com
{::include contributor.yml}

normative:

informative:


--- abstract

A transport network is a server-layer network to provide connectivity
services to its client.  In this draft the tunnel of client is
described, with the definition of client tunnel YANG model.

--- middle

# Introduction

   A transport network is a server-layer network designed to provide
   connectivity services for a client-layer network to carry the client
   traffic transparently across the server-layer network resources.  The
   tunnel model in Traffic-Engineered network has been defined in both
   generic way and technology-specific way.  The generic model, which is
   the base TE tunnel YANG model, can be found at
   {{!I-D.ietf-teas-yang-te}}.  Technology-specific models, such as OTN/
   WSON tunnel model, have also been defined in
   {{?I-D.ietf-ccamp-otn-tunnel-model}} and
   {{?I-D.ietf-ccamp-wson-tunnel-model}} respectively.  Corresponding
   tunnel on client-layer is also required, to have a complete topology
   view from the perspective of network controllers.

   This document defines a data model of all client-layer tunnel, using
   YANG language defined in {{!RFC7950}}.  The model is augmenting the
   generic TE tunnel model, and can be used by applications exposing to
   a network controller via a REST interface.  Furthermore, it can be
   used by an application to describe the client tunnel that constructed
   above the server-layer network.  It is also worth noting that the
   client layer network will only need the tunnel model when there is a
   demand for switching techniques, such as Carrier Ethernet and MPLS-
   TP.  The transparent signals do not need this model.

# Terminology and Notations

   A simplified graphical representation of the data model is used in
   this document.  The meaning of the symbols in the YANG data tree
   presented later in this document is defined in {{?RFC8340}}.  They are
   provided below for reference.

- Brackets "\[" and "]" enclose list keys.

- Abbreviations before data node names: "rw" means configuration
(read-write) and "ro" state data (read-only).

- Symbols after data node names: "?" means an optional node, "!"
means a presence container, and "*" denotes a list and leaf-list.

- Parentheses enclose choice and case nodes, and case nodes are also
marked with a colon (":").

- Ellipsis ("...") stands for contents of subtrees that are not
shown.

# YANG Model for Client-layer Tunnel

## YANG Tree for Ethernet Tunnel

~~~~ ascii-art
{::include ietf-eth-te-tunnel.tree}
~~~~
{: #fig-eth-topology-tree title="Ethernet TE Tunnel YANG tree" artwork-name="ietf-eth-te-tunnel.tree"}

## YANG Tree for Tunnel of other Client Signal Model

This section will be completed later.

# YANG Code for Client-layer Tunnel

## The ETH Tunnel YANG Code

~~~~ yang
{::include ietf-eth-te-tunnel.yang}
~~~~
{: #fig-te-yang title="Ethernet TE Tunnel YANG module"
sourcecode-markers="true" sourcecode-name="ietf-eth-te-tunnel@2018-03-01.yang"}

## Other Client-layer Tunnel YANG Code

TBD.

# Considerations and Open Issue

Editor Notes: This section is used to note temporary discussion/
conclusion that to be fixed in the future version, and will be
removed before publication.  This is a part of L2 work, need to
discuss how to go with other L2 network models.  The expectation is
to include all potential L2 TE part in this work.

# IANA Considerations

   TBD.

# Manageability Considerations

   TBD.

# Security Considerations

The data following the model defined in this document is exchanged
via, for example, the interface between an orchestrator and a
transport network controller.  The security concerns mentioned in
{{!I-D.ietf-teas-yang-te}} also applies to this document.

The YANG module defined in this document can be accessed via the
RESTCONF protocol defined in {{!RFC8040}}, or maybe via the NETCONF
protocol {{!RFC6241}}.

--- back

# Acknowledgments
{:numbered="false"}

We would like to thank Igor Bryskin and Daniel King for their
comments and discussions.
