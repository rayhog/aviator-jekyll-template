---
title: /TQL
position: 1.1
type: get
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
  sensitive.

  {: .success}


  Adds a book to your collection.
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
right_code_blocks:
  - code_block: "SOFTWARE CATEGORIES\r\nAccounting\r\nAlerts and Monitoring Tools\r\nAnalytics\r\nAnti Virus and Malware\r\nApplication Architecture and Design\r\nApplication Servers\r\nApplication Testing and QA\r\nArchiving and Content Storage\r\nBackup and Recovery\r\nBanking\r\nBlogs & Wikis\r\nBusiness Intelligence (BI) Suites\r\nBusiness Metrics and Reporting Tools\r\nBusiness Performance Management\r\nCapacity Planning\r\nCartography/Mapping\r\nCD & DVD Recording\r\nCollaboration Platforms\r\nCompiler and Decompiler\r\nComputer Hardware Configuration Management\r\nComputer-Based Training\r\nConferencing\r\nConfiguration Management Database (CMDB)\r\nConnectivity Tools\r\nContent Delivery and Distribution\r\nCross-Industry ERP Suites\r\nCustomer Relationship Management (CRM) Suites\r\nCustomer Service & Support\r\nData Mining and Warehousing\r\nData Security and Encryption\r\nDemand Management\r\nDesktop Enhancements\r\nDesktop Publishing (DTP)\r\nDevelopment Environment\r\nDictionary and Encyclopedia\r\nDistribution and Transportation Management\r\nDocument and Records Management\r\nDocument Capturing and Imaging\r\nDrivers\r\nElectronic Design Automation\r\nEnterprise\r\nEnterprise Integration\r\nFault Management\r\nFile Managers\r\nFinancial Management\r\nFinancial Management Suites\r\nFirewall and Intrusion Prevention\r\nGames\r\nGraphics and Image Editing\r\nHardware Virtualization\r\nHelp and Service Desk\r\nHospital Management\r\nHypervisor\r\nIBM i\r\nIdentity and Access Management\r\nIndustry-Specific ERP Suites\r\nInstant Messaging\r\nInsurance\r\nInventory Management\r\nInvestment\r\nIT Asset Maintenance & Support\r\nIT Asset Management\r\nLicense Management\r\nLife Sciences\r\nLifestyle and Personal Improvement\r\nLocation-Aware Services\r\nMac OS\r\nMail Servers\r\nMainframe\r\nManufacturing Process Management\r\nMarketing Management\r\nMathematics and Physics\r\nMechanical CAD, CAM, and CAE Software\r\nMedical software\r\nMerchandising\r\nMultimedia Players\r\nNavigation Tools\r\nNetwork Performance Management\r\nOther Educational Software\r\nOther Engineering & Scientific Software\r\nOther Entertainment Software\r\nOther Hobbies Software\r\nOther Multimedia and Graphics Tools\r\nOther Operating Systems\r\nOther References Software\r\nOther Utilities\r\nPayment Systems\r\nPayroll & Time Accounting\r\nPeer-to-peer (P2P) Networking\r\nPersonal\r\nPIM & Contact Managers\r\nPlant/Shop Control\r\nPoint of Sale\r\nPresence\r\nPresentation\r\nProcurement and Sourcing\r\nProduct and Portfolio Management\r\nProduct Data Management\r\nProduct Design\r\nProductivity Suites\r\nRecruitment & Training\r\nRegulatory and Compliance Management\r\nReligious Software\r\nSales and Operations Planning\r\nSales Management\r\nSecurity Suites\r\nSocial Networking\r\nSoftware Configuration Management\r\nSoftware Virtualization\r\nSpatial Analysis\r\nSports Software\r\nSpreadsheets\r\nStorage Resource Management\r\nStorage Virtualization\r\nStore Operations\r\nSupplier Relationship Management\r\nSupply Chain Management (SCM) Suites\r\nSynchronization Tools\r\nTaxation\r\nUnclassified Middleware\r\nUnclassified Software\r\nUNIX\r\nVideo and Audio Editing\r\nVirtualization Management Software\r\nVulnerability Management\r\nWarehouse Management System\r\nWeb Browsers\r\nWeb Content Management\r\nWeb Design\r\nWeb Servers\r\nWindows\r\nWord Processors\r\nWorkflow and Business Process Management\r\nWorkforce Management\r\n"
    title: SOFTWARE CATEGORIES
    language: html
  - code_block: "SOFTWARE NODE TYPE ATTRIBUTES\r\ncat_sw_product_id\_| int\r\nalias\_| text\r\ncomponent\_| text\r\ncat_sw_product_desupported_flag\_| text\r\ncat_sw_product_discontinued_flag\_| text\r\nfamily\_| text\r\nis_suite\_| bool\r\nnfamily\_| bool\r\nplicsable\_| bool\r\ntitle\_| text\r\ncat_sw_product_url\_| text\r\nvendor_category\_| text\r\ncat_sw_product_id\_| int\r\ncat_sw_edition_desupported_flag\_| boolean\r\nedition\_| text\r\nedition_order\_| int\r\ncat_sw_edition_url\_| text\r\ncat_sw_product_id\_| int\r\ncloud\_| text\r\ncat_sw_release_id\_| int\r\ncat_sw_major_release_id\_| int\r\ncat_sw_release_desupported_flag\_| boolean\r\ncat_sw_release_discontinued_flag\_| boolean\r\nga_date| text\r\nis_major\_| text\r\nlicensable\_| boolean\r\ncat_sw_release_patchlevel\_| text\r\nrelease\_| boolean\r\nunverified_version\_| boolean\r\ncat_sw_release_url\_| text\r\ncat_sw_version_id\_| int\r\ncat_sw_major_version_id\_| int\r\ncat_sw_version_desupported_flag\_| boolean\r\nis_major_version\_| boolean\r\ncat_sw_version_patchlevel\_| text\r\nsubversion\_| text\r\nversion\_| text\r\nversion_order\_| int\r\ncat_sw_version_group_id\_| int\r\nversion_group\_| text\r\ncat_sw_suite_id\_| int\r\ncat_sw_suite_desupported_flag\_| boolean\r\nsuite\_| text\r\ncat_sw_pricing_id\_| int\r\navg_price\_| float\r\nmax_price\_| float\r\nmin_price\_| float\r\ncat_currency_id\_| int\r\ncurrency_code\_| text\r\ncat_sw_rel_lifecycle_id\_| int\r\nend_of_life\_| timestamp\r\nend_of_life_exception\_| text\r\nend_of_life_range_end\_| timestamp\r\nend_of_life_range_start\_| timestamp\r\nend_of_life_str\_| text\r\nend_of_life_support_level\_| text\r\nga_exception\_| text\r\nga_range_end\_| timestamp\r\nga_range_start\_| timestamp\r\ngeneral_availability\_| timestamp\r\ngeneral_availability_str\_| text\r\nobsolete\_| timestamp\r\nobsolete_exception\_| text\r\nobsolete_range_end\_| timestamp\r\nobsolete_range_start\_| timestamp\r\nobsolete_str\_| text\r\nobsolete_support_level\_| text\r\ncat_sw_rel_platform_id\_| int\r\ncat_sw_rel_platform_desupported_flag\_| boolean\r\ncat_sw_rel_platform_discontinued_flag\_| boolean\r\nhas_fingerprint\_| boolean\r\nplatform_label\_| text\r\nplatform_type\_| text\r\nrelease_platform\_| text\r\ncat_sw_rel_supp_stage_id\_| int\r\ndate_end_date\_| timestamp\r\nrelease_support_stage\_| text\r\nstage_order\_| int\r\ncat_windows10_compatibility_id\_| int\r\nwin10_32bit_compat_status\_| int\r\nwin10_32bit_compat_status_desc\_| text\r\nwin10_32bit_compat_upg_path\_| text\r\nwin10_32bit_compat_date\_| timestamp\r\nwin10_32bit_readiness\_| text\r\nwin10_64bit_compat_status\_| int\r\nwin10_64bit_compat_status_desc\_| text\r\nwin10_64bit_compat_upg_path\_| text\r\nwin10_64bit_compat_date\_| timestamp\r\nwin10_64bit_readiness\_| text\r\ncat_windows8_compatibility_id\_| int\r\nwin8_32bit_compat_status\_| int\r\nwin8_32bit_compat_status_desc\_| text\r\nwin8_32bit_compat_upgrade_path\_| text\r\nwin8_32bit_compat_date\_| timestamp\r\nwin8_32bit_readiness\_| text\r\nwin8_64bit_compat_status\_| int\r\nwin8_64bit_compat_status_desc\_| text\r\nwin8_64bit_compat_upgrade_path\_| text\r\nwin8_64bit_compat_date\_| timestamp\r\nwin8_64bit_readiness\_| text\r\ncat_windows7_compatibility_id\_| int\r\nwin7_32bit_compat_status\_| int\r\nwin7_32bit_compat_status_desc\_| text\r\nwin7_32bit_compat_upgrade_path\_| text\r\nwin7_32bit_compat_date\_| timestamp\r\nwin7_32bit_readiness\_| text\r\nwin7_64bit_compat_status\_| int\r\nwin7_64bit_compat_status_desc\_| text\r\nwin7_64bit_compat_upgrade_path\_| text\r\nwin7_64bit_compat_date\_| timestamp\r\nwin7_64bit_readiness\_| text\r\n"
    title: SOFTWARE NODE ATTRIBUTES
    language: html
  - code_block: "NODE TYPES\r\nSOFTWARE\r\nHARDWARE\_\r\nMANUFACTURER\r\nCPU\_\r\nCVE\r\nSOFTWARE_LICENSE\r\nHARDWARE_LICENSE\_\r\n"
    title: NODE TYPES
    language:
---


