---
title: Software Product
position: 1.8
type:
description: >-
  Create Query for example query. In this example, we will pull data from
  Technopedia that contains 'excel'.
parameters:
  - name: title
    content: The title for the book
  - name: score
    content: The book's score between 0 and 5
content_markdown: >-
  The query returns software that includes 'Excel'. This is query is case
  sensitive. {: .success} MATCH (n:SOFTWARE\_PRODUCT) WHERE n.title = "PDF
  Converter" RETURN n {: .success} Adds a book to your collection.
left_code_blocks:
  - code_block: |-
      {
          "results": [
              {
                  "s": {
                      "attributes": {
                          "title": "Total Access 900 Series IP Business Gateway"
                      },
                      "created_at": "2017-11-17T13:29:54.555Z",
                      "created_by": "00000000-0000-0000-0000-000000000000",
                      "label": "HARDWARE",
                      "owner": "00000000-0000-0000-0000-000000000000",
                      "quality_grade": 3,
                      "technopedia_id": "7f4f7044-e0de-4da9-87b1-817266df9684"
                  }
              },
              {
                  "s": {
                      "attributes": {
                          "title": "Total Access 900 Series IP Business Gateway"
                      },
                      "created_at": "2017-11-17T13:29:54.555Z",
                      "created_by": "00000000-0000-0000-0000-000000000000",
                      "label": "HARDWARE",
                      "owner": "00000000-0000-0000-0000-000000000000",
                      "quality_grade": 3,
                      "technopedia_id": "f35c4a08-785e-4b3b-93c6-3588b298e976"
                  }
              },
              {
                  "s": {
                      "attributes": {
                          "title": "Total Access 900e Series IP Business Gateway"
                      },
                      "created_at": "2017-11-17T13:29:54.555Z",
                      "created_by": "00000000-0000-0000-0000-000000000000",
                      "label": "HARDWARE",
                      "owner": "00000000-0000-0000-0000-000000000000",
                      "quality_grade": 3,
                      "technopedia_id": "f620a8b5-c928-4adb-8047-6ca2d1375d7a"
                  }
              },
    title: GET
    language: json
  - code_block: >
      MATCH (<Node_Type>:<alias> {<attribute>: '<attribute_value>'}) RETURN
      <alias>

      MATCH (SOFTWARE:s {category: 'Web Browsers'}) RETURN s.title


      SAMPLE RESPONSE

      {
          "version": "1.0.0",
          "request-id": "a3505e21-8d91-40ff-b587-3f6731a1086b",
          "results": [
              {
                  "s": {
                      "attributes": {
                          "end_of_life_str": "1/9/2007",
                          "title": "Excel for Mac",
                          "version": "10.0"
                      },
                      "created_at": "2017-11-17T12:15:47.158Z",
                      "created_by": "00000000-0000-0000-0000-000000000000",
                      "label": "SOFTWARE",
                      "owner": "00000000-0000-0000-0000-000000000000",
                      "quality_grade": 3,
                      "technopedia_id": "2b0e74ee-b8c0-4a6d-a096-a892fbaed1fc"
                  }
              },
    title: QUERY EXAMPLE AND RESPONSE
    language: bash
  - code_block: |-
      MATCH (n:SOFTWARE_PRODUCT) 
      WHERE n.title = "PDF Converter" 
      RETURN n
    title: Match Query
    language: json
  - code_block: |-

      [
        {
          "keys": [
            "n"
          ],
          "length": 1,
          "_fields": [
            {
              "identity": {
                "low": 57619464,
                "high": 0
              },
              "labels": [
                "SOFTWARE_PRODUCT"
              ],
              "properties": {
                "product_url": "http://welcome.hp.com/country/us/en/prodserv/software/eda/pdf/HowToDownloadSoftware.pdf",
                "software": "PDF Converter",
                "cat_sw_product_id": "441336845",
                "created_at": "2017-08-28 12:56:27",
                "title": "PDF Converter",
                "is_suite": "FALSE",
                "vendor_category": "Converter",
                "cat_manufacturer_id": "7796",
                "technopedia_id": "\\x6a9a4000083f685ae0530100007f9f25",
                "nfamily": "TRUE",
                "plicsable": "1",
                "alias": "HP Exstream PDF Converter",
                "modified_at": "2017-08-28 12:56:27",
                "family": "Exstream"
              }
            }[   {   
    title: Response Example
    language: json
right_code_blocks:
  - code_block: |
      SOFTWARE CATEGORIES
      _____________________________________
      Accounting
      Alerts and Monitoring Tools
      Analytics
      Anti Virus and Malware
      Application Architecture and Design
      Application Servers
      Application Testing and QA
      Archiving and Content Storage
      Backup and Recovery
      Banking
      Blogs & Wikis
      Business Intelligence (BI) Suites
      Business Metrics and Reporting Tools
      Business Performance Management
      Capacity Planning
      Cartography/Mapping
      CD & DVD Recording
      Collaboration Platforms
      Compiler and Decompiler
      Computer Hardware Configuration Management
      Computer-Based Training
      Conferencing
      Configuration Management Database (CMDB)
      Connectivity Tools
      Content Delivery and Distribution
      Cross-Industry ERP Suites
      Customer Relationship Management (CRM) Suites
      Customer Service & Support
      Data Mining and Warehousing
      Data Security and Encryption
      Demand Management
      Desktop Enhancements
      Desktop Publishing (DTP)
      Development Environment
      Dictionary and Encyclopedia
      Distribution and Transportation Management
      Document and Records Management
      Document Capturing and Imaging
      Drivers
      Electronic Design Automation
      Enterprise
      Enterprise Integration
      Fault Management
      File Managers
      Financial Management
      Financial Management Suites
      Firewall and Intrusion Prevention
      Games
      Graphics and Image Editing
      Hardware Virtualization
      Help and Service Desk
      Hospital Management
      Hypervisor
      IBM i
      Identity and Access Management
      Industry-Specific ERP Suites
      Instant Messaging
      Insurance
      Inventory Management
      Investment
      IT Asset Maintenance & Support
      IT Asset Management
      License Management
      Life Sciences
      Lifestyle and Personal Improvement
      Location-Aware Services
      Mac OS
      Mail Servers
      Mainframe
      Manufacturing Process Management
      Marketing Management
      Mathematics and Physics
      Mechanical CAD, CAM, and CAE Software
      Medical software
      Merchandising
      Multimedia Players
      Navigation Tools
      Network Performance Management
      Other Educational Software
      Other Engineering & Scientific Software
      Other Entertainment Software
      Other Hobbies Software
      Other Multimedia and Graphics Tools
      Other Operating Systems
      Other References Software
      Other Utilities
      Payment Systems
      Payroll & Time Accounting
      Peer-to-peer (P2P) Networking
      Personal
      PIM & Contact Managers
      Plant/Shop Control
      Point of Sale
      Presence
      Presentation
      Procurement and Sourcing
      Product and Portfolio Management
      Product Data Management
      Product Design
      Productivity Suites
      Recruitment & Training
      Regulatory and Compliance Management
      Religious Software
      Sales and Operations Planning
      Sales Management
      Security Suites
      Social Networking
      Software Configuration Management
      Software Virtualization
      Spatial Analysis
      Sports Software
      Spreadsheets
      Storage Resource Management
      Storage Virtualization
      Store Operations
      Supplier Relationship Management
      Supply Chain Management (SCM) Suites
      Synchronization Tools
      Taxation
      Unclassified Middleware
      Unclassified Software
      UNIX
      Video and Audio Editing
      Virtualization Management Software
      Vulnerability Management
      Warehouse Management System
      Web Browsers
      Web Content Management
      Web Design
      Web Servers
      Windows
      Word Processors
      Workflow and Business Process Management
      Workforce Management
    title: SOFTWARE CATEGORIES
    language: bash
  - code_block: "SOFTWARE NODE TYPE ATTRIBUTES\ncat_sw_product_id\_| int\nalias\_| text\ncomponent\_| text\ncat_sw_product_desupported_flag\_| text\ncat_sw_product_discontinued_flag\_| text\nfamily\_| text\nis_suite\_| bool\nnfamily\_| bool\nplicsable\_| bool\ntitle\_| text\ncat_sw_product_url\_| text\nvendor_category\_| text\ncat_sw_product_id\_| int\ncat_sw_edition_desupported_flag\_| boolean\nedition\_| text\nedition_order\_| int\ncat_sw_edition_url\_| text\ncat_sw_product_id\_| int\ncloud\_| text\ncat_sw_release_id\_| int\ncat_sw_major_release_id\_| int\ncat_sw_release_desupported_flag\_| boolean\ncat_sw_release_discontinued_flag\_| boolean\nga_date| text\nis_major\_| text\nlicensable\_| boolean\ncat_sw_release_patchlevel\_| text\nrelease\_| boolean\nunverified_version\_| boolean\ncat_sw_release_url\_| text\ncat_sw_version_id\_| int\ncat_sw_major_version_id\_| int\ncat_sw_version_desupported_flag\_| boolean\nis_major_version\_| boolean\ncat_sw_version_patchlevel\_| text\nsubversion\_| text\nversion\_| text\nversion_order\_| int\ncat_sw_version_group_id\_| int\nversion_group\_| text\ncat_sw_suite_id\_| int\ncat_sw_suite_desupported_flag\_| boolean\nsuite\_| text\ncat_sw_pricing_id\_| int\navg_price\_| float\nmax_price\_| float\nmin_price\_| float\ncat_currency_id\_| int\ncurrency_code\_| text\ncat_sw_rel_lifecycle_id\_| int\nend_of_life\_| timestamp\nend_of_life_exception\_| text\nend_of_life_range_end\_| timestamp\nend_of_life_range_start\_| timestamp\nend_of_life_str\_| text\nend_of_life_support_level\_| text\nga_exception\_| text\nga_range_end\_| timestamp\nga_range_start\_| timestamp\ngeneral_availability\_| timestamp\ngeneral_availability_str\_| text\nobsolete\_| timestamp\nobsolete_exception\_| text\nobsolete_range_end\_| timestamp\nobsolete_range_start\_| timestamp\nobsolete_str\_| text\nobsolete_support_level\_| text\ncat_sw_rel_platform_id\_| int\ncat_sw_rel_platform_desupported_flag\_| boolean\ncat_sw_rel_platform_discontinued_flag\_| boolean\nhas_fingerprint\_| boolean\nplatform_label\_| text\nplatform_type\_| text\nrelease_platform\_| text\ncat_sw_rel_supp_stage_id\_| int\ndate_end_date\_| timestamp\nrelease_support_stage\_| text\nstage_order\_| int\ncat_windows10_compatibility_id\_| int\nwin10_32bit_compat_status\_| int\nwin10_32bit_compat_status_desc\_| text\nwin10_32bit_compat_upg_path\_| text\nwin10_32bit_compat_date\_| timestamp\nwin10_32bit_readiness\_| text\nwin10_64bit_compat_status\_| int\nwin10_64bit_compat_status_desc\_| text\nwin10_64bit_compat_upg_path\_| text\nwin10_64bit_compat_date\_| timestamp\nwin10_64bit_readiness\_| text\ncat_windows8_compatibility_id\_| int\nwin8_32bit_compat_status\_| int\nwin8_32bit_compat_status_desc\_| text\nwin8_32bit_compat_upgrade_path\_| text\nwin8_32bit_compat_date\_| timestamp\nwin8_32bit_readiness\_| text\nwin8_64bit_compat_status\_| int\nwin8_64bit_compat_status_desc\_| text\nwin8_64bit_compat_upgrade_path\_| text\nwin8_64bit_compat_date\_| timestamp\nwin8_64bit_readiness\_| text\ncat_windows7_compatibility_id\_| int\nwin7_32bit_compat_status\_| int\nwin7_32bit_compat_status_desc\_| text\nwin7_32bit_compat_upgrade_path\_| text\nwin7_32bit_compat_date\_| timestamp\nwin7_32bit_readiness\_| text\nwin7_64bit_compat_status\_| int\nwin7_64bit_compat_status_desc\_| text\nwin7_64bit_compat_upgrade_path\_| text\nwin7_64bit_compat_date\_| timestamp\nwin7_64bit_readiness\_| text\n"
    title: SOFTWARE NODE ATTRIBUTES
    language: bash
  - code_block: "NODE TYPES\nSOFTWARE\nHARDWARE\_\nMANUFACTURER\nCPU\_\nCVE\nSOFTWARE_LICENSE\nHARDWARE_LICENSE\_\n"
    title: NODE TYPES
    language: bash
  - code_block: "PARAMETER\t                TYPE\tDESCRIPTION\ncat_sw_product_id\_\t        integer\tProduct ID\nalias\_\t                    text\tAlias\ncat_sw_product_id\_\t        integer\tProduct ID\nalias\_\t                    text\tAlias\ncat_sw_product_id\_\t        integer\tProduct ID\nalias\_\t                    text\tAlias"
    title: Software Node Attribues
    language:
---

