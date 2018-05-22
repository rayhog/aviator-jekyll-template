---
title: Software Product
position: 1.15
type:
description: >-
  Create Query for example query. In this example, we will pull data from
  Technopedia that contains 'excel'.
content_markdown: >-
  The query returns software that includes 'Excel'. This is query is case
  sensitive. 
  
  {: .success} 
  
  MATCH (n:SOFTWARE\_PRODUCT) WHERE n.title = "PDF Converter" RETURN n 
left_code_blocks:
  - code_block: "\r\nMATCH (n:SOFTWARE_PRODUCT) \r\nWHERE n.title = \"PDF Converter\" \r\nRETURN n"
    title: MATCH SOFTWARE_PRODUCT
    language: bash
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
      SOFTWARE VERSION ATTRIBUTES
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
      title: SOFTWARE VERSION ATTRIBUTES
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

