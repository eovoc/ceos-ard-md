# Best Practices and Recommendations

## Community Approaches

The INSPIRE, DGIWG and Linked Data communities (W3C DCAT) have adopted well-documented approaches for expressing conformance of data products with quality related data product specifications.  These can be applied in the CEOS context to express compliance with CEOS-ARD Product Family Specifications {cite}`CEOS_ARD` or other CEOS Specifications (e.g. WGISS Data Management and Stewardship Maturity Matrix conformance {cite}`ceos_mm`).

Section 3.1.4 "Data quality info" of the INSPIRE Metadata Technical Guidance {cite}`inspire_metadata_guidance` provides specific 
guidelines on how to include a statement on the degree of conformity with the specifications against which its conformity has been 
evaluated.  The same approach is used by [DGIWG](https://dgiwg.org/documents/dgiwg-standards) {cite}`dgiwg_standards`  in §5.4.2.4 "Conformance Result" of the "DGIWG Metadata Foundation" specification {cite}`dgiwg_dmf`.  

Section [14.2.1](https://www.w3.org/TR/vocab-dcat-3/#quality-conformance-statement) of DCAT {cite}`dcat_v3` contains general guidelines to be applied when expressing compliance with a standard in metadata:  

- Use the URI of the standard / specification. E.g., to express conformance of a dcat:CatalogRecord with DCAT, the URI to be used is https://www.w3.org/TR/vocab-dcat/.
- Use the canonical, persistent URI. This is usually specified in the document itself. If you are in doubt, use the one included in the bibliographic citations for that standard / specification.
- Use the non-versioned URI. If you need to express conformance with a specific version of the standard / specification, use both the un-versioned and the versioned URI

## Application to CEOS-ARD

`````{admonition} CEOS-ARDMD-REC-0010 [Recommendation]
:class: tip
If a collection is conformant with all requirements of a CEOS-ARD data specification (threshold), it
is recommended to include information on the conformance with the specification.  
`````


`````{admonition} CEOS-ARDMD-REC-0020 [Recommendation]
:class: tip
If a collection is not yet conformant with all requirements of a CEOS-ARD data specification, it
is recommended to include information on the conformance with the individual conformance classes (if any).  
`````
This approach is recommended by {cite}`inspire_dataspec_oi`.

Alternatively, or in addition, a simple keyword-based identification of CEOS-ARD Product Families can be adoped as well, using codelist and codelist values. This approach is described as well.


## Metadata Encoding

In the following subsections, Best Practices are presented for encoding conformance results and controlled keywords in a number of widely used metadata formats.

### ISO19139 Encoding

This section describes best practices for ISO 19139 {cite}`iso19139` and ISO 19139-1 {cite}`iso19139_1` collection metadata encoding.

Section 3.1.4 "Data quality info" of the INSPIRE Metadata Technical Guidance {cite}`inspire_metadata_guidance` defines how to express 
conformance with a specification or a compliance class.

- Conformance to a specification:
    - The URI of the actual specification is included as `xlink:href` in the `/gmd:title/gmx:anchor` element of the `gmd:specification` (TG Rec 1.11).
- Conformance to a compliance class of a specification
    - The URI of the conformance class can be specified as `xlink:href` in the `/gmd:title/gmx:anchor` element of the `gmd:specification` (TG Rec 1.12).    



    
Section 8.1.1 "Data quality info" recommendations 16 to 21 of the INSPIRE Data Specification on Orthoimagery – Technical Guidelines {cite}`inspire_dataspec_oi` can be adopted.  They are similar to the above but state:

- Conformance to a specification:
    - The URI of the specification is included as `xlink:href` in the `gmd:specification` (Rec 21).
- Conformance to a compliance class of a specification
    - The URI of the conformance class can be specified as `xlink:href` in the `/gmd:title/gmx:anchor` element of the `gmd:specification` (Rec 21).  

Instead of including a complete citation of the specification, the following short notation is allowed according to {cite}`inspire_dataspec_oi` as well.

```{index} single: conformance ; ISO19139
```

> **Example: 1.1**  
>  Documenting conformance with specification in ISO19139 metadata (without citation).

```xml
<gmd:DQ_ConformanceResult>
    <gmd:specification xlink:href="https://ceos.org/ard/files/PFS/NRB/v5.5"/>
    <gmd:explanation>
			<gco:CharacterString>See the referenced specification</gco:CharacterString>
	</gmd:explanation>
	<gmd:pass>
		<gco:Boolean>true</gco:Boolean>
	</gmd:pass>
</gmd:DQ_ConformanceResult>
```

Possible results that can be expressed are:

- true if conformant
- false if not conformant
- null (with nilReason) is not evaluated.


If conformance is not evaluated, the result should be as follows according to {cite}`inspire_metadata_guidance`. 

```xml
	<gmd:pass gco:nilReason="unknown"/>
```


> **Example: 1.2**  
>  Documenting conformance with specification or conformance class in ISO19139 metadata (with citation).

Note that the specification URI is not inside the `specification` element but in a `gmx:Anchor` element as {cite}`inspire_metadata_guidance` allows adding there a reference to a citation document instead, so the two approaches are not consistent.

Data quality section as proposed in the INSPIRE Metadata Technical Guidance {cite}`inspire_metadata_guidance`

```xml
<?xml version="1.0" encoding="UTF-8"?>
<gmi:MI_Metadata xmlns:gmi="http://www.isotc211.org/2005/gmi"
                 xmlns:gco="http://www.isotc211.org/2005/gco"
                 xmlns:gmd="http://www.isotc211.org/2005/gmd"
                 xmlns:gmx="http://www.isotc211.org/2005/gmx"
                 xmlns:xlink="http://www.w3.org/1999/xlink"
                 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
                 xsi:schemaLocation="http://www.isotc211.org/2005/gmi ./gmi/gmi.xsd">
	<gmd:dataQualityInfo xmlns:gmd="http://www.isotc211.org/2005/gmd">
		<gmd:DQ_DataQuality>
			<gmd:scope>
				<gmd:DQ_Scope>
					<gmd:level>
						<gmd:MD_ScopeCode codeList="http://www.tc211.org/ISO19139/resources/codeList.xml#MD_ScopeCode"
						                  codeListValue="series"/>
					</gmd:level>
				</gmd:DQ_Scope>
			</gmd:scope>
			<gmd:report>
				<gmd:DQ_ConceptualConsistency>
					<gmd:result>
						<gmd:DQ_ConformanceResult>
							<gmd:specification>
								<gmd:CI_Citation>
									<gmd:title>
										<gmx:Anchor xlink:href="https://ceos.org/ard/files/PFS/NRB/v5.5">CEOS-ARD Product Family Specification: Normalised Radar Backscatter</gmx:Anchor>
									</gmd:title>
									<gmd:date>
										<gmd:CI_Date>
											<gmd:date>
												<gco:Date>2021-10-14</gco:Date>
											</gmd:date>
											<gmd:dateType>
												<gmd:CI_DateTypeCode codeList="https://standards.iso.org/iso/19139/resources/gmxCodelists.xml#CI_DateTypeCode"
												                     codeListValue="publication"/>
											</gmd:dateType>
										</gmd:CI_Date>
									</gmd:date>
								</gmd:CI_Citation>
							</gmd:specification>
							<gmd:explanation>
								<gco:CharacterString>See the referenced specification</gco:CharacterString>
							</gmd:explanation>
							<gmd:pass>
								<gco:Boolean>true</gco:Boolean>
							</gmd:pass>
						</gmd:DQ_ConformanceResult>
					</gmd:result>
				</gmd:DQ_DomainConsistency>
			</gmd:report>
		</gmd:DQ_DataQuality>
	</gmd:dataQualityInfo>
```


`````{admonition} CEOS-ARDMD-REC-1010 [Recommendation]
:class: tip
Collection metadata records in ISO19139(-2) format should advertise conformance status with respect to CEOS-ARD PFS using a citation element with reference to the document URI or conformance class URI as shown in example 1.2. 
`````


> **Example: 1.3**  
>  Documenting conformance with specification ISO19139 metadata (with keywords).

```xml
<gmd:descriptiveKeywords xmlns:gmx="http://www.isotc211.org/2005/gmx">
	<gmd:MD_Keywords>
		<gmd:keyword>
			<gmx:Anchor xlink:href="https://ceos.org/ard/metadata-codelists/PFS/NRB">Normalised Radar Backscatter</gmx:Anchor>
		</gmd:keyword>
		<gmd:thesaurusName>
			<gmd:CI_Citation>
				<gmd:title>
					<gmx:Anchor xlink:href="https://ceos.org/ard/metadata-codelists/PFS">CEOS-ARD Product Family Specification</gmx:Anchor>
				</gmd:title>
				<gmd:date/>
			</gmd:CI_Citation>
		</gmd:thesaurusName>
	</gmd:MD_Keywords>
</gmd:descriptiveKeywords>
```


### ISO19115-3 Encoding

This section describes best practices for ISO 19115-3 {cite}`iso19115_3` collection metadata encoding.  It relies on the ISO19157-2 {cite}`iso19157_2` XML schema implementation for Data Quality.


> **Example: 2.1**  
>  Documenting conformance with specification or conformance class in ISO19115-3 metadata (without citation).

```xml
<?xml version="1.0" encoding="UTF-8"?>
<mdb:MD_Metadata xmlns:mdb="http://standards.iso.org/iso/19115/-3/mdb/1.0"
                 xmlns:gco="http://standards.iso.org/iso/19115/-3/gco/1.0"
                 xmlns:mcc="http://standards.iso.org/iso/19115/-3/mcc/1.0"
                 xmlns:mdq="http://standards.iso.org/iso/19157/-2/mdq/1.0"
                 xmlns:xlink="http://www.w3.org/1999/xlink"
                 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
	<mdb:dataQualityInfo>
		<mdq:DQ_DataQuality>
			<mdq:scope>
				<mcc:MD_Scope>
					<mcc:level>
						<mcc:MD_ScopeCode codeList="http://standards.iso.org/ittf/PubliclyAvailableStandards/ISO_19139_Schemas/resources/codelist/gmxCodelists.xml#MD_ScopeCode" 
										  codeListValue="series"/>
					</mcc:level>
				</mcc:MD_Scope>
			</mdq:scope>
			<mdq:report>
				<mdq:DQ_DomainConsistency>
					<mdq:result>
						<mdq:DQ_ConformanceResult>
							<mdq:specification xlink:href="https://ceos.org/ard/files/PFS/NRB/v5.5/CARD4L-PFS_NRB_v5.5.pdf"/>
							<mdq:explanation>
								<gco:CharacterString>See the referenced specification</gco:CharacterString>
							</mdq:explanation>
							<mdq:pass>
								<gco:Boolean>true</gco:Boolean>
							</mdq:pass>
						</mdq:DQ_ConformanceResult>
					</mdq:result>
				</mdq:DQ_DomainConsistency>
			</mdq:report>
		</mdq:DQ_DataQuality>
	</mdb:dataQualityInfo>
</mdb:MD_Metadata>
```

> **Example: 2.2**  
>  Documenting conformance with specification or conformance class in ISO19115-3 metadata (with citation).


```xml
<?xml version="1.0" encoding="UTF-8"?>
<mdb:MD_Metadata xmlns:mdb="http://standards.iso.org/iso/19115/-3/mdb/1.0"
                 xmlns:cit="http://standards.iso.org/iso/19115/-3/cit/1.0"
                 xmlns:gco="http://standards.iso.org/iso/19115/-3/gco/1.0"
                 xmlns:gcx="http://standards.iso.org/iso/19115/-3/gcx/1.0"
                 xmlns:mcc="http://standards.iso.org/iso/19115/-3/mcc/1.0"
                 xmlns:mdq="http://standards.iso.org/iso/19157/-2/mdq/1.0"
                 xmlns:xlink="http://www.w3.org/1999/xlink"
                 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">

	<mdb:dataQualityInfo>
		<mdq:DQ_DataQuality>
			<mdq:scope>
				<mcc:MD_Scope>
					<mcc:level>
						<mcc:MD_ScopeCode codeList="http://www.tc211.org/ISO19139/resources/codeList.xml#MD_ScopeCode"
						                  codeListValue="series"/>
					</mcc:level>
				</mcc:MD_Scope>
			</mdq:scope>
			<mdq:report>
				<mdq:DQ_DomainConsistency>
					<mdq:result>
						<mdq:DQ_ConformanceResult>
							<mdq:specification>
								<cit:CI_Citation>
									<cit:title>
										<gcx:Anchor xlink:href="https://ceos.org/ard/files/PFS/NRB/v5.5">CEOS-ARD Product Family Specification: Normalised Radar Backscatter</gcx:Anchor>
									</cit:title>
									<cit:date>
										<cit:CI_Date>
											<cit:date>
												<gco:Date>2021-10-14</gco:Date>
											</cit:date>
											<cit:dateType>
												<cit:CI_DateTypeCode codeList="https://standards.iso.org/iso/19115/resources/Codelists/cat/codelists.xml#CI_DateTypeCode"
												                     codeListValue="publication"/>
											</cit:dateType>
										</cit:CI_Date>
									</cit:date>
								</cit:CI_Citation>
							</mdq:specification>
							<mdq:explanation>
								<gco:CharacterString>See the referenced specification</gco:CharacterString>
							</mdq:explanation>
							<mdq:pass>
								<gco:Boolean>true</gco:Boolean>
							</mdq:pass>
						</mdq:DQ_ConformanceResult>
					</mdq:result>
				</mdq:DQ_DomainConsistency>
			</mdq:report>
		</mdq:DQ_DataQuality>
	</mdb:dataQualityInfo>
</mdb:MD_Metadata>
```

`````{admonition} CEOS-ARDMD-REC-2010 [Recommendation]
:class: tip
Collection metadata records in ISO19115-3 {cite}`iso19115_3` format should advertise conformance status with respect to CEOS-ARD PFS using a citation element with reference to the document URI or conformance class URI as shown in example 2.2. 
`````



> **Example: 2.3**  
>  Documenting conformance with specification in ISO19115-3 metadata with additional information about evaluation method, self assessment, peer review etc.

```xml
<mdb:dataQualityInfo>
		<mdq:DQ_DataQuality>
			<mdq:scope>
				<mcc:MD_Scope>
					<mcc:level>
						<mcc:MD_ScopeCode codeList="http://www.tc211.org/ISO19139/resources/codeList.xml#MD_ScopeCode" codeListValue="series"/>
					</mcc:level>
				</mcc:MD_Scope>
			</mdq:scope>
			<mdq:report>
				<mdq:DQ_ConceptualConsistency>
					<mdq:measure>
						<mdq:DQ_MeasureReference>
							<mdq:measureIdentification>
								<mcc:MD_Identifier>
									<mcc:authority>
										<cit:CI_Citation>
											<cit:title>
												<gco:CharacterString>International Organization for Standardization</gco:CharacterString>
											</cit:title>
											<cit:alternateTitle>
												<gco:CharacterString>ISO</gco:CharacterString>
											</cit:alternateTitle>
											<cit:date/>
										</cit:CI_Citation>
									</mcc:authority>
									<mcc:code>
										<gco:CharacterString>101</gco:CharacterString>
									</mcc:code>
									<mcc:codeSpace>
										<gco:CharacterString>https://standards.isotc211.org/19157/-3/1/dqc/content/qualityMeasure/</gco:CharacterString>
									</mcc:codeSpace>
								</mcc:MD_Identifier>
							</mdq:measureIdentification>
							<mdq:nameOfMeasure>
								<gco:CharacterString>Data product specification passed</gco:CharacterString>
							</mdq:nameOfMeasure>
							<mdq:measureDescription>
								<gco:CharacterString>Indication that all requirements in the referred data product specification are fulfilled.</gco:CharacterString>
							</mdq:measureDescription>
						</mdq:DQ_MeasureReference>
					</mdq:measure>
					<mdq:evaluationMethod>
						<mdq:DQ_FullInspection>
							<mdq:evaluationMethodDescription>
								<gco:CharacterString>CEOS WGCV evaluation</gco:CharacterString>
							</mdq:evaluationMethodDescription>
							<mdq:evaluationProcedure>
								<cit:CI_Citation>
									<cit:title>
										<gco:CharacterString>CEOS-ARD Normalised Radar Backscatter</gco:CharacterString>
									</cit:title>
									<cit:date>
										<cit:CI_Date>
											<cit:date>
												<gco:Date>2021-10-14</gco:Date>
											</cit:date>
											<cit:dateType>
												<cit:CI_DateTypeCode codeList="https://standards.iso.org/iso/19115/resources/Codelists/cat/codelists.xml#CI_DateTypeCode" 
																	 codeListValue="publication"/>
											</cit:dateType>
										</cit:CI_Date>
									</cit:date>
									<cit:edition>
										<gco:CharacterString>5.5</gco:CharacterString>
									</cit:edition>
									<cit:onlineResource>
										<cit:CI_OnlineResource>
											<cit:linkage>
												<gco:CharacterString>https://ceos.org/ard/files/PFS/NRB/v5.5</gco:CharacterString>
											</cit:linkage>
											<cit:name>
												<gco:CharacterString>Specification</gco:CharacterString>
											</cit:name>
											<cit:function>
												<cit:CI_OnLineFunctionCode codeList="http://standards.iso.org/ittf/PubliclyAvailableStandards/ISO_19139_Schemas/resources/codelist/ML_gmxCodelists.xml#CI_OnLineFunctionCode" 
																		   codeListValue="information"/>
											</cit:function>
										</cit:CI_OnlineResource>
									</cit:onlineResource>
									<cit:onlineResource>
										<cit:CI_OnlineResource>
											<cit:linkage>
												<gco:CharacterString>https://ceos.org/ard/files/Self%20Assessments/NRB/v5.5/NovaSAR_CSIRO_SelfAssessment.zip</gco:CharacterString>
											</cit:linkage>
											<cit:name>
												<gco:CharacterString>Self assessment</gco:CharacterString>
											</cit:name>
											<cit:function>
												<cit:CI_OnLineFunctionCode codeList="http://standards.iso.org/ittf/PubliclyAvailableStandards/ISO_19139_Schemas/resources/codelist/ML_gmxCodelists.xml#CI_OnLineFunctionCode" 
																		   codeListValue="information"/>
											</cit:function>
										</cit:CI_OnlineResource>
									</cit:onlineResource>
									<cit:onlineResource>
										<cit:CI_OnlineResource>
											<cit:linkage>
												<gco:CharacterString>https://ceos.org/ard/files/Peer%20Reviews/NRB/v5.5/NovaSAR_WGCVEval.zip</gco:CharacterString>
											</cit:linkage>
											<cit:name>
												<gco:CharacterString>Peer review</gco:CharacterString>
											</cit:name>
											<cit:function>
												<cit:CI_OnLineFunctionCode codeList="http://standards.iso.org/ittf/PubliclyAvailableStandards/ISO_19139_Schemas/resources/codelist/ML_gmxCodelists.xml#CI_OnLineFunctionCode" 
																		   codeListValue="information"/>
											</cit:function>
										</cit:CI_OnlineResource>
									</cit:onlineResource>
								</cit:CI_Citation>
							</mdq:evaluationProcedure>
						</mdq:DQ_FullInspection>
					</mdq:evaluationMethod>
					<mdq:result>
						<mdq:DQ_ConformanceResult>
							<mdq:specification>
								<cit:CI_Citation>
									<cit:title>
										<gcx:Anchor xlink:href="https://ceos.org/ard/files/PFS/NRB/v5.5">CEOS-ARD Product Family Specification: Normalised Radar Backscatter</gcx:Anchor>
									</cit:title>
									<cit:date>
										<cit:CI_Date>
											<cit:date>
												<gco:Date>2021-10-14</gco:Date>
											</cit:date>
											<cit:dateType>
												<cit:CI_DateTypeCode codeList="https://standards.iso.org/iso/19115/resources/Codelists/cat/codelists.xml#CI_DateTypeCode" 
																	 codeListValue="publication"/>
											</cit:dateType>
										</cit:CI_Date>
									</cit:date>
								</cit:CI_Citation>
							</mdq:specification>
							<mdq:explanation>
								<gco:CharacterString>See the referenced specification</gco:CharacterString>
							</mdq:explanation>
							<mdq:pass>
								<gco:Boolean>true</gco:Boolean>
							</mdq:pass>
						</mdq:DQ_ConformanceResult>
					</mdq:result>
				</mdq:DQ_ConceptualConsistency>
			</mdq:report>
		</mdq:DQ_DataQuality>
	</mdb:dataQualityInfo>
```


> **Example: 2.4**  
>  Documenting conformance with specification in ISO19115-3 metadata (with keywords).

```xml
<mri:descriptiveKeywords>
	<mri:MD_Keywords>
		<mri:keyword>
			<gcx:Anchor xlink:href="https://ceos.org/ard/metadata-codelists/PFS/NRB">Normalised Radar Backscatter</gcx:Anchor>
		</mri:keyword>
		<mri:thesaurusName>
			<cit:CI_Citation>
				<cit:title>
					<gcx:Anchor xlink:href="https://ceos.org/ard/metadata-codelists/PFS">CEOS-ARD Product Family Specification</gcx:Anchor>
				</cit:title>
				<cit:date/>
			</cit:CI_Citation>
		</mri:thesaurusName>
	</mri:MD_Keywords>
</mri:descriptiveKeywords>
```


Example files:
    - [novasar_l2ard_hh_hv_1.xml](./examples/iso19115-3/novasar_l2ard_hh_hv_1.xml)
    - [novasar_l2ard_hh_hv_2.xml](./examples/iso19115-3/novasar_l2ard_hh_hv_2.xml)


### ISO19115-4 Encoding

This section describes best practices for ISO 19115-4 {cite}`iso19115_4` collection metadata encoding.



> **Example: 3.1**  
>  Documenting conformance with specification or conformance class in ISO19115-4 {cite}`iso19115_4` metadata (with citation).


```json
{
        "dataQualityInfo": [
            {
                "scope": {
                    "level": "series"
                },
                "report": [
                    {
                        "measure": {
                            "measureIdentification": {
                                "code": "101",
                                "codeSpace": "https://standards.isotc211.org/19157/-3/1/dqc/content/qualityMeasure/"
                            },
                            "nameOfMeasure": ["data product specification passed"],
                            "measureDescription": "Indication that all requirements in the referred data product specification are fulfilled."
                        },
                        "result": [
                            {
                                "pass": true,
                                "specification": {
                                    "date": {
                                        "publication": "2021-10-14"
                                    },
                                    "identifier": [
                                        {
                                            "code": "https://ceos.org/ard/files/PFS/SR/v5.0.1",
                                            "codeSpace": "https://ceos.org/ard"
                                        }
                                    ],
                                    "edition": "5.0",
                                    "title": "CEOS-ARD Product Family Specification: Surface Reflectance"
                                },
                                "type": "ConformanceResult",
                                "explanation": "See the referenced specification"
                            }
                        ],                
                        "type": "DomainConsistency"
                    }
                ]
            }
        ]   
}
```

> **Example: 3.2**  
>  Documenting conformance with specification in ISO19115-4 metadata with additional information about evaluation method, self assessment, peer review, sampling ratio etc.




```json
{
    "dataQualityInfo": [
        {
            "scope": {
                "level": "series"
            },
            "report": [
                {
                    "measure": {
                            "measureIdentification": {
                                "code": "101",
                                "codeSpace": "https://standards.isotc211.org/19157/-3/1/dqc/content/qualityMeasure/"
                            },
                            "nameOfMeasure": ["data product specification passed"],
                            "measureDescription": "Indication that all requirements in the referred data product specification are fulfilled."
                        },
                    "result": [{
                                "pass": true,
                                "specification": {
                                    "date": {
                                        "publication": "2021-10-14"
                                    },
                                    "identifier": [
                                        {
                                            "code": "https://ceos.org/ard/files/PFS/NRB/v5.5",
                                            "codeSpace": "tbd"
                                        }
                                    ],
                                    "edition": "5.5",
                                    "title": "CEOS-ARD Product Family Specification: Normalised Radar Backscatter"
                                },
                                "type": "ConformanceResult",
                                "explanation": "See the referenced specification"
                            }
                        ],
                       
                        "evaluationMethod": [{
                                "referenceDoc": [],
                                "evaluationProcedure": {
                                    "editionDate": "2021-10-14",
                                    "edition": "5.5",
                                    "onlineResource": [{
                                            "name": "Specification",
                                            "function": "information",
                                            "linkage": "https://ceos.org/ard/files/PFS/NRB/v5.5/CARD4L-PFS_NRB_v5.5.pdf"
                                        }, {
                                            "name": "Self assessment",
                                            "function": "information",
                                            "linkage": "https://ceos.org/ard/files/Self20Assessments/NRB/v5.5/Opera%20RTC%20Sentinel-1%20self-assessment.zip"
                                        }, {
                                            "name": "Peer review",
                                            "function": "information",
                                            "linkage": "https://ceos.org/ard/files/Peer%20Reviews/NRB/v5.5/NovaSAR_WGCVEval.zip"
                                        }
                                    ],
                                    "title": "CEOS-ARD Normalised Radar Backscatter"
                                },
                                "samplingRatio": "unknown.",
                                "samplingScheme": "See Peer review report.",
                                "lotDescription": "31 PFS metadata items.  See ee Peer review report for additional detail.",
                                "type": "SampleBasedInspection",
                                "evaluationMethodDescription": "CEOS WGCV evaluation"
                            }
                        ]
                }
                ]
        }
        ]
}

```

`````{admonition} CEOS-ARDMD-REC-3010 [Recommendation]
:class: tip
Collection metadata records in ISO19115-4 {cite}`iso19115_4` format should advertise conformance status with respect to CEOS-ARD PFS using a citation element with reference to the document URI or conformance class URI as shown in example 3.1. 
`````

> **Example: 3.3**  
>  Documenting conformance with specification in ISO19115-4 metadata (with keywords).

```json
{
	"identificationInfo": {
    	"defaultLocale": {
        	"language": "eng",
    		"characterEncoding": "utf8"
        },
        "extent": [{"geographicElement": [{
        	"northBoundLatitude": 38.42053289934906,
            "southBoundLatitude": -55.94470669421993,
            "type": "EX_GeographicBoundingBox",
            "westBoundLongitude": -62.87262834116111,
            "eastBoundLongitude": 173.246741777445
        }]}],
        "descriptiveKeywords": [{
            "thesaurusName": {
				"title": "CEOS-ARD Product Family Specification"
			},
            "keyword": ["Normalised Radar Backscatter"]
        }],
        "citation": {
            "date": {"creation": "2025-10-20"},
            "title": "novasar_l2ard_hh_hv"
        },
        "abstract": "NovaSAR-1 CEOS-ARD (level 2) HH,HV polarizations"
    }	
}
```


Example files:
    - [novasar_l2ard_hh_hv.json](./examples/iso19115-4/novasar_l2ard_hh_hv.json)

### STAC Encoding

This section describes best practices for STAC {cite}`stac` collection metadata encoding.

The proposed encoding uses the draft STAC CEOS-ARD Extension {cite}`stac_ceos_ard`  


> **Example: 4.1**  
>  Documenting conformance with specification or conformance class in STAC collection {cite}`stac` metadata using the STAC CEOS-ARD Extension {cite}`stac_ceos_ard`.



```json
{
  "stac_version": "1.0.0",
  "type": "Collection",
  "title": "EnMAP L2A HSI Products",

  "ceosard:specification": "SR",
  "ceosard:type": "optical",
  "ceosard:specification_version": "5.0",
  
  "links": [
    {
      "rel": "ceos-ard-specification",
      "href": "https://ceos.org/ard/files/PFS/SR/v5.0/CARD4L_Product_Family_Specification_Surface_Reflectance-v5.0.pdf",
      "type": "application/pdf",
      "title": "CEOS-ARD Product Family Specification for Surface Reflectance (PDF)"
    },
    {
      "rel": "ceos-ard-assessment",
      "href": "https://ceos.org/ard/files/Self%20Assessments/SR/v5.0/Response_Review_comments_EnMAP_CARD4L_Product_Family_Specification_Surface_Reflectance-v5.pdf",
      "type": "application/pdf",
      "title": "Peer assessment"
    },

  ],
  "id": "ENMAP_HSI_L2A",
  "stac_extensions": [
      "https://stac-extensions.github.io/ceos-ard/v0.2.0/schema.json"
  ]
}
```



```{warning}
The STAC CEOS-ARD Extension {cite}`stac_ceos_ard` properties `ceosard:specification and specification_version` do currently not allow to express that a collection is conformant with more than one CEOS-ARD Product Famility Specification.
```


TBD: could the "document identifier" redirect to the PDF to not have the detailed PDF filename to identify the specification ?

```json
"links": [
  {
      "rel": "ceos-ard-specification",
      "href": "https://ceos.org/ard/files/PFS/SR/v5.0",
      "type": "text/html",
      "title": "Surface Reflectance (CARD4L-SR)"
  }
] 
```


Alternatively, the lightweight approach with controlled keywords can be used.

> **Example: 4.2**  
>  Documenting conformance with specification in STAC collection {cite}`stac` metadata using keywords and the STAC Themes Extension {cite}`stac_theme_extension`.


```json
{
  "stac_version": "1.0.0",
  "type": "Collection",
  "title": "EnMAP L2A HSI Products",

  "themes": [{
    "concepts": [{
      "id": "SR",
      "title": "Surface Reflectance",
      "url": "https://ceos.org/ard/metadata-codelists/PFS/SR"
    }],
    "scheme": "https://ceos.org/ard/metadata-codelists/PFS"
  }],

  "id": "ENMAP_HSI_L2A",
  "stac_extensions": [
    "https://stac-extensions.github.io/themes/v1.0.0/schema.json"
  ]
}
```

`````{admonition} CEOS-ARDMD-REC-4010 [Recommendation]
:class: tip
Collection metadata records in STAC {cite}`stac` format should advertise conformance status with respect to CEOS-ARD PFS using the STAC CEOS-ARD Extension {cite}`stac_ceos_ard` with reference to the document URI as shown in example 4.1. 
`````

Example files:
    - [ENMAP_HSI_L2A.json](./examples/stac/ENMAP_HSI_L2A.json)

### DIF10 Encoding

This section describes best practices for DIF10 {cite}`dif10` collection metadata encoding.

> **Example: 5.1**  
>  Documenting conformance with specification or conformance class in DIF10 {cite}`dif10` metadata.

TBD


> **Example: 5.3**  
>  Documenting conformance with specification in DIF10 {cite}`dif10` metadata (with keywords).

```xml
<?xml version="1.0" encoding="UTF-8"?>
<DIF 
	xmlns="http://gcmd.gsfc.nasa.gov/Aboutus/xml/dif/" 
	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
	xsi:schemaLocation="http://gcmd.gsfc.nasa.gov/Aboutus/xml/dif/ https://git.earthdata.nasa.gov/projects/EMFD/repos/dif-schemas/raw/10.x/dif_v10.2.xsd">
	<Entry_ID>
		<Short_Name>novasar_l2ard_hh_hv</Short_Name>
		<Version>NA</Version>
	</Entry_ID>

	<Extended_Metadata>
		<Metadata>
			<Group>org.ceos</Group>
			<Name>https://ceos.org/ard/metadata-codelists/PFS</Name>
			<Value>NRB</Value>
			<Value>Normalised Radar Backscatter</Value>
		</Metadata>
	</Extended_Metadata>
</DIF>
```


### UMM-JSON Encoding

This section describes best practices for UMM-JSON {cite}`umm_json` collection metadata encoding.
TBD

> **Example: 6.1**  
>  Documenting conformance with specification or conformance class in UMM-JSON metadata.


> **Example: 6.3**  
>  Documenting conformance with specification in UMM-JSON {cite}`umm_json` metadata (with keywords).



### GeoDCAT-AP Encoding

This section describes best practices for GeoDCAT-AP {cite}`geodcat_ap` collection metadata encoding based on DCAT {cite}`dcat_v3`.
The encoding is valid for the RDF/XML, Turtle and JSON-LD serialisations.
The proposed encoding is derived from the guidance in the [ISO19139 to DCAT-AP](https://github.com/GeoCat/iso-19139-to-dcat-ap/blob/master/documentation/Mappings.md#mapping-conformance-result) mappings.

Additional information is available at:
- https://semiceu.github.io/GeoDCAT-AP/releases/3.0.0/#conformance-test-results
- https://semiceu.github.io/GeoDCAT-AP/releases/3.0.0/#conformity-and-data-quality---not-in-iso19115-core



> **Example: 7.1**  
>  Documenting conformance with specification or conformance class in GeoDCAT-AP metadata.


```xml
<rdf:RDF xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#"
         xmlns:rdfs="http://www.w3.org/2000/01/rdf-schema#"
         xmlns:dct="http://purl.org/dc/terms/"
         xmlns:prov="http://www.w3.org/ns/prov#"
         xmlns:dcat="http://www.w3.org/ns/dcat#"
         xmlns:xsd="http://www.w3.org/2001/XMLSchema#">
	<dcat:Dataset rdf:about="https://fedeo.ceos.org/collections/novasar_l2ard_hh_hv">
		<dct:conformsTo>
			<dct:Standard rdf:about="https://ceos.org/ard/files/PFS/NRB/v5.5">
				<dct:title>CEOS-ARD Product Family Specification: Normalised Radar Backscatter</dct:title>
				<dct:identifier>https://ceos.org/ard/files/PFS/NRB/v5.5</dct:identifier>
				<dct:hasVersion>5.5</dct:hasVersion>
				<rdfs:seeAlso rdf:resource="https://ceos.org/ard/files/PFS/NRB/v5.5/CARD4L-PFS_NRB_v5.5.pdf"/>
			</dct:Standard>
		</dct:conformsTo>
	</dcat:Dataset>
</rdf:RDF>	
```


> **Example: 7.2**  
>  Documenting conformance with specification or conformance class in GeoDCAT-AP metadata (without citation).


```xml
<rdf:RDF xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#"
         xmlns:rdfs="http://www.w3.org/2000/01/rdf-schema#"
         xmlns:dct="http://purl.org/dc/terms/"
         xmlns:prov="http://www.w3.org/ns/prov#"
         xmlns:dcat="http://www.w3.org/ns/dcat#"
         xmlns:xsd="http://www.w3.org/2001/XMLSchema#">
	<dcat:Dataset rdf:about="https://fedeo.ceos.org/collections/novasar_l2ard_hh_hv">
		<prov:wasUsedBy>
			<prov:Activity>
				<prov:qualifiedAssociation rdf:parseType="Resource">
					<prov:hadPlan rdf:parseType="Resource">
						<!-- Specification -->
						<prov:wasDerivedFrom rdf:resource="https://ceos.org/ard/files/PFS/NRB/v5.5"/>
					</prov:hadPlan>
				</prov:qualifiedAssociation>
				<!-- Conformance result / conformity degree -->
				<prov:generated rdf:parseType="Resource">
					<dct:type rdf:resource="http://inspire.ec.europa.eu/metadata-codelist/DegreeOfConformity/conformant"/>
					<dct:description xml:lang="en">See the referenced specification</dct:description>
				</prov:generated>
			</prov:Activity>
		</prov:wasUsedBy>
	</dcat:Dataset>
</rdf:RDF>	
```

The same example in Turtle is shown below.

```
@prefix dcat: <http://www.w3.org/ns/dcat#> .
@prefix prov: <http://www.w3.org/ns/prov#> .
@prefix dc: <http://purl.org/dc/terms/> .

<https://fedeo.ceos.org/collections/novasar_l2ard_hh_hv>
  a dcat:Dataset ;
  prov:wasUsedBy [
    a prov:Activity ;
    prov:qualifiedAssociation [ prov:hadPlan [ prov:wasDerivedFrom <https://ceos.org/ard/files/PFS/NRB/v5.5> ] ] ;
    prov:generated [
      dc:type <http://inspire.ec.europa.eu/metadata-codelist/DegreeOfConformity/conformant> ;
      dc:description "See the referenced specification"@en
    ]
  ] .
```

Possible values are defined in the [INSPIRE codelist](https://inspire.ec.europa.eu/metadata-codelist/DegreeOfConformity):

- conformant
- notConformant
- notEvaluated

> **Example: 7.3**  
>  Documenting conformance with specification or conformance class in GeoDCAT-AP metadata (with citation).


```xml
<rdf:RDF xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#"
         xmlns:rdfs="http://www.w3.org/2000/01/rdf-schema#"
         xmlns:dct="http://purl.org/dc/terms/"
         xmlns:prov="http://www.w3.org/ns/prov#"
         xmlns:dcat="http://www.w3.org/ns/dcat#"
         xmlns:xsd="http://www.w3.org/2001/XMLSchema#">
	<dcat:Dataset rdf:about="https://fedeo.ceos.org/collections/novasar_l2ard_hh_hv">
		<prov:wasUsedBy>
			<prov:Activity>
				<prov:qualifiedAssociation rdf:parseType="Resource">
					<prov:hadPlan rdf:parseType="Resource">
						<!-- Specification -->
						<prov:wasDerivedFrom>
							<rdf:Description rdf:about="https://ceos.org/ard/files/PFS/NRB/v5.5">
								<dct:title xml:lang="en">CEOS-ARD Product Family Specification: Normalised Radar Backscatter</dct:title>
								<dct:hasVersion>5.5</dct:hasVersion>
								<dct:issued rdf:datatype="http://www.w3.org/2001/XMLSchema#date">2010-12-08</dct:issued>
								<dct:publisher rdf:resource="http://dbpedia.org/resource/Committee_on_Earth_Observation_Satellites"/>
							</rdf:Description>
						</prov:wasDerivedFrom>
					</prov:hadPlan>
				</prov:qualifiedAssociation>
				<!-- Conformance result / conformity degree -->
				<prov:generated rdf:parseType="Resource">
					<dct:type rdf:resource="http://inspire.ec.europa.eu/metadata-codelist/DegreeOfConformity/conformant"/>
					<dct:description xml:lang="en">See the referenced specification</dct:description>
				</prov:generated>
			</prov:Activity>
		</prov:wasUsedBy>
	</dcat:Dataset>
</rdf:RDF>	
```
The same example in Turtle is shown below.

```
@prefix dcat: <http://www.w3.org/ns/dcat#> .
@prefix prov: <http://www.w3.org/ns/prov#> .
@prefix dc: <http://purl.org/dc/terms/> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

<https://fedeo.ceos.org/collections/novasar_l2ard_hh_hv>
  a dcat:Dataset ;
  prov:wasUsedBy [
    a prov:Activity ;
    prov:qualifiedAssociation [ prov:hadPlan [ prov:wasDerivedFrom <https://ceos.org/ard/files/PFS/NRB/v5.5> ] ] ;
    prov:generated [
      dc:type <http://inspire.ec.europa.eu/metadata-codelist/DegreeOfConformity/conformant> ;
      dc:description "See the referenced specification"@en
    ]
  ] .

<https://ceos.org/ard/files/PFS/NRB/v5.5>
  dc:title "CEOS-ARD Product Family Specification: Normalised Radar Backscatter"@en ;
  dc:hasVersion "5.5" ;
  dc:issued "2010-12-08"^^xsd:date ;
  dc:publisher <http://dbpedia.org/resource/Committee_on_Earth_Observation_Satellites> .
```


> **Example: 7.4**  
>  Documenting conformance with specification in GeoDCAT-AP {cite}`geodcat_ap` metadata (with keywords).

```json
{
	"@context": {},
	"@type": "dcat:Dataset",
  	"dct:type": "http://inspire.ec.europa.eu/metadata-codelist/ResourceType/series",
  	"dct:identifier": "novasar_l2ard_hh_hv",	
    "dct:description": "NovaSAR-1 CEOS-ARD (level 2) HH,HV polarizations",
  	"dcat:theme": [{
    	"skos:prefLabel": "Normalised Radar Backscatter",
    	"@type": "skos:Concept",
    	"@id": "https://ceos.org/ard/metadata-codelists/PFS/NRB",
    	"skos:inScheme": "https://ceos.org/ard/metadata-codelists/PFS"
  	}],
  	"@id": "https://emc.spacebel.be/collections/novasar_l2ard_hh_hv",
  	"dct:title": "novasar_l2ard_hh_hv"
}
```


`````{admonition} CEOS-ARDMD-REC-7010 [Recommendation]
:class: tip
Collection metadata records in GeoDCAT-AP {cite}`geodcat_ap` format (in RDF/XML, Turtle or JSON-LD serialisation) should advertise conformance status with respect to CEOS-ARD PFS using a citation element with dct:title and reference to the document URI or conformance class URI (rdf:Description) as shown in example 7.3. 
`````

### OGC 17-084r1 Encoding

This section describes best practices for OGC 17-084r1 {cite}`OGC_17_084r1` collection metadata encoding.


> **Example: 8.1**  
>  Documenting conformance with specification or conformance class in OGC 17-084r1 {cite}`OGC_17_084r1` metadata.

```json
{
  "geometry": {
  },
  "id": "https://fedeo.ceos.org/collections/novasar_l2ard_hh_hv",
  "type": "Feature",
  "properties": {
    "date": "2019-11-02T02:32:55.000Z/2025-10-08T12:05:22.999Z",
    "identifier": "novasar_l2ard_hh_hv",
    "wasUsedBy": [{
      "generated": {
        "degree": "http://inspire.ec.europa.eu/metadata-codelist/DegreeOfConformity/conformant",
        "description": "See the referenced specification",
        "type": "Entity"
      },
      "qualifiedAssociation": {
        "hadPlan": {
          "wasDerivedFrom": {
            "type": "Standard",
            "issued": "2021-10-14T00:00:00.00Z"
          },
          "type": "Plan"
        },
        "type": "Association"
      },
      "type": "Activity"
    }],
    "contactPoint": [{
      "hasAddress": {
        "postal-code": "ACT 2601",
        "street-address": "Building 101, Clunies Ross Street",
        "locality": "Black Mountain",
        "country-name": "Australia"
      },
      "phone": "tel:+61395452176",
      "name": "CSIRO",
      "type": "Organization",
      "uri": "www.csiro.au"
    }],
    "kind": "http://purl.org/dc/dcmitype/Collection",
    "created": "2025-10-20T00:00:00.000Z",
    "abstract": {"text/plain": "NovaSAR-1 CEOS-ARD (level 2) HH,HV polarizations"},
    "title": "novasar_l2ard_hh_hv",
    "links": {
      "previews": [{
        "href": "https://eo-data.csiro.au/projects/easi-thumbnails/novasar_l2ard_hh_hv/2019/11/CEOS-ARD_NRB_v5_5_NovaSAR_01_7940_scd_29_191102_023255_HH_HV_A_R-ql.png",
        "title": "graphic overview",
        "type": "image/png"
      }],
      "alternates": [
      ]
    },
    "categories": [{
      "scheme": "https://ceos.org/ard/metadata-codelists/PFS",
      "term": "https://ceos.org/ard/metadata-codelists/PFS/NRB",
      "label": "Normalised Radar Backscatter"
    }],
    "isPrimaryTopicOf": {
      "created": "2025-10-20T00:00:00.00Z",
      "conformsTo": {
        "versionInfo": "2005/Cor.1:2006",
        "type": "Standard",
        "title": "ISO19115"
      },
      "type": "CatalogRecord",
      "lang": "en",
      "updated": "2025-10-20T00:00:00.00Z"
    },
    "updated": "2025-10-20T00:00:00.000Z"
  }
}
```



> **Example: 8.2**  
>  Documenting conformance with specification in OGC 17-084r1 {cite}`OGC_17_084r1` metadata using controlled keywords.

```json
    "categories": [
      {
        "scheme": "https://gcmd.earthdata.nasa.gov/kms/concepts/concept_scheme/platforms",
        "term": "https://gcmd.earthdata.nasa.gov/kms/concept/edd3cc77-31a1-4ed3-8da4-64a9554aa6fa",
        "label": "EnMAP"
      },
      {
        "scheme": "https://gcmd.earthdata.nasa.gov/kms/concepts/concept_scheme/instruments",
        "term": "https://gcmd.earthdata.nasa.gov/kms/concept/5455b670-66d7-417b-b616-877b94caafe0",
        "label": "HSI"
      },
      {
        "scheme": "https://ceos.org/ard/metadata-codelists/PFS",
        "term": "https://ceos.org/ard/metadata-codelists/PFS/SR",
        "label": "Surface Reflectance"
      }
    ]
```


`````{admonition} CEOS-ARDMD-REC-8010 [Recommendation]
:class: tip
Collection metadata records in {cite}`OGC_17_084r1` format should advertise conformance status with respect to CEOS-ARD PFS using the STAC CEOS-ARD Extension {cite}`stac_ceos_ard` with reference to the document URI as shown in example 8.1. 
`````

Example files:
    - [novasar_l2ard_hh_hv.json](./examples/ogc17-084r1/novasar_l2ard_hh_hv.json)



## Traceability

TBD: mapping of proposed requirements to source documents and metadata formats.