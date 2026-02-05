# Best Practices and Recommendations

## Community Approaches

The INSPIRE, DGIWG and Linked Data communities (W3C DCAT) have adopted well-documented approaches for expressing conformance of data products with quality related data product specifications.  These can be applied in the CEOS context to express compliance with CEOS-ARD Product Family Specifications {cite}`CEOS_ARD` or other CEOS Specifications (e.g. Maturity Matrix conformance {cite}`ceos_mm`).

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

Alternatively, or in addition, a simple keyword-based identification of EOS-ARD Product Families can be adoped as well, using codelist and codelist values. This approach is described as well.


## Metadata Model

These guidelines can be applied to the various flavours of metadata specifications covered in the remainder of this document.

To apply the above high level requirements, the following information related to CEOS specifications or more precisely CEOS-ARD Product Family specifications should be agreed:

- Document citations, including precise title, date and document identifier (URI)
- Conformance class identifiers (URI) - when used in future specifications.

### Requirements for Citations

The proposed recommendations assume that CEOS-ARD Product Family specifications (PFS) will in the future use identification of documents and conformance classes similar to current OGC practice.

For example, OGC identifies specification documents and conformance classes using URI.

| Specification Title | Version | External identifier (URI) |
|------|-----|-----|
| OGC API - Processes - Part 1: Core | 1.0.0 | http://www.opengis.net/doc/IS/ogcapi-processes-1/1.0 | 
| OGC API - Features - Part 1: Core | 1.0 |  http://www.opengis.net/doc/IS/ogcapi-features-1/1.0 | 

Winthin documents, conformance classes are defined via URI as well.

| Specification Title | Version |  Conformance Class Example | Conformance Class Example (URI)
|------|-----|-----|-----|
| OGC API - Processes - Part 1: Core | 1.0.0  | Core | http://www.opengis.net/spec/ogcapi-processes-1/1.0/conf/core |
| OGC API - Features - Part 1: Core | 1.0 | GeoJSON | http://www.opengis.net/spec/ogcapi-features-1/1.0/conf/geojson | 

As the above practices are not yet in place for CEOS-ARD specification, we assume the following identifiers.  They will be updated once the final identifiers are available.

Below are a number of the current specifications.  They are meant as examples and the recommendations should apply to all current and 
future specifications.  Note that the "title" to be used in citations of the various PFS (e.g. NRB) may currently not be well defined.

| Specification Title | Version | Date | External identifier (URI) |
|------|-----|-----|-----|
| CEOS-ARD Product Family Specification: Surface Reflectance | 5.0.1 | 6/12/2023 | https://ceos.org/ard/files/PFS/SR/v5.0.1 | 
| CEOS-ARD Product Family Specification: Normalised Radar Backscatter | 5.5 | 14/10/2021 | https://ceos.org/ard/files/PFS/NRB/v5.5 | 
| CEOS-ARD Product Family Specification: Surface Temperature | 5.0 | 08/06/2020 | https://ceos.org/ard/files/PFS/ST/v5.0 | 

```{warning}
Do we want to preserve the folder names currently used as URI to identify the actual documents ? or will documents get different URI on the cover sheet as per OGC practice ?.
```

It should be noted that the above identifiers are not the actual download URL which are:

- https://ceos.org/ard/files/PFS/SR/v5.0.1/CEOS-ARD_Product_Family_Specification_Surface_Reflectance-v5.0.1.pdf
- https://ceos.org/ard/files/PFS/NRB/v5.5/CARD4L-PFS_NRB_v5.5.pdf 
- https://ceos.org/ard/files/PFS/ST/v5.0/CARD4L_Product_Family_Specification_Surface_Temperature-v5.0.pdf

The current PFS specifications do currently not define conformance classes.  These may be added at a later stage and will allow to express partial compliance.

```{warning}
URI and meaning of compliance classes have still to be defined.  Below are examples only...
```

| Specification Title | Version |  Conformance Class  | Conformance Class (URI)
|------|-----|-----|-----|
| CEOS-ARD Product Family Specification: Surface Reflectance          | 5.0   | Threshold | http://ceos.org/spec/ard/PFS/SR/5.0/conf/threshold  |
| CEOS-ARD Product Family Specification: Surface Reflectance          | 5.0   | Threshold | http://ceos.org/spec/ard/PFS/SR/5.0/conf/threshold_geometric_correction  |
| CEOS-ARD Product Family Specification: Surface Reflectance          | 5.0   | Threshold | http://ceos.org/spec/ard/PFS/SR/5.0/conf/target_geometric_correction  |
| CEOS-ARD Product Family Specification: Normalised Radar Backscatter | 5.5   | Threshold | http://ceos.org/spec/ard/PFS/NRB/5.5/conf/threshold | 


`````{admonition} CEOS-ARDMD-REC-0020 [Recommendation]
:class: tip
Metadata encoding shall use citation elements for CEOS-ARD PFS such as document titles, document identifiers (URI) and conformence class identifiers (URI) according to the conventions summarized above. 
`````

### Requirements for Keywords

An alternative lightweight approach consists in including controlled keywords in the collection metadata to categorize the colections according to 
CEOS-ARD Product Family.  This approach is not suitable to express compliance with individual conformance classes however.

The following controlled keywords are proposed and may be discoverable in the future via the publication of an `https://ceos.org/ard/resources/codelists.xml` document.  This approach mimics the way ISO publishes codelists, e.g. https://standards.iso.org/iso/19139/resources/gmxCodelists.xml.


```xml

<?xml version="1.0" encoding="UTF-8"?>
<!-- 2026-01-30 -->
<CT_CodelistCatalogue 
    xmlns="http://www.isotc211.org/2005/gmx" 
    xmlns:gco="http://www.isotc211.org/2005/gco" xmlns:gml="http://www.opengis.net/gml/3.2" 
    xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
    xsi:schemaLocation="http://www.isotc211.org/2005/gmx http://standards.iso.org/ittf/PubliclyAvailableStandards/ISO_19139_Schemas/gmx/gmx.xsd http://www.isotc211.org/2005/gco http://standards.iso.org/ittf/PubliclyAvailableStandards/ISO_19139_Schemas/gco/gco.xsd http://www.opengis.net/gml/3.2 http://standards.iso.org/ittf/PubliclyAvailableStandards/ISO_19136_Schemas/gml.xsd http://www.w3.org/1999/xlink http://www.w3.org/1999/xlink.xsd">
	<!--=====Catalogue description=====-->
	<name>
		<gco:CharacterString>ardCodelists</gco:CharacterString>
	</name>
	<scope>
		<gco:CharacterString>Codelists for description of metadata datasets compliant with CEOS-ARD Froduct Family Specifications</gco:CharacterString>
	</scope>
	<fieldOfApplication>
		<gco:CharacterString>CEOS-ARD</gco:CharacterString>
	</fieldOfApplication>
	<versionNumber>
		<gco:CharacterString>0.0</gco:CharacterString>
	</versionNumber>
	<versionDate>
		<gco:Date>2026-01-30</gco:Date>
	</versionDate>

	<!--============================= Codelists =======================================-->
	<!--=== CI_DateTypeCode ===-->
	<codelistItem>
		<CodeListDictionary gml:id="ARD_PFSCode">
			<gml:description>Product Family Specification</gml:description>
			<gml:identifier codeSpace="CEOS/ARD">ARD_PFSCode</gml:identifier>
			<codeEntry>
				<CodeDefinition gml:id="ARD_PFSCode_NRB">
					<gml:description>Normalised Radar Backscatter</gml:description>
					<gml:identifier codeSpace="CEOS/ARD">NRB</gml:identifier>
				</CodeDefinition>
			</codeEntry>
			<codeEntry>
				<CodeDefinition gml:id="ARD_PFSCode_SR">
					<gml:description>Surface Reflectance</gml:description>
					<gml:identifier codeSpace="CEOS/ARD">SR</gml:identifier>
				</CodeDefinition>
			</codeEntry>
		</CodeListDictionary>
	</codelistItem>
	<!--=== EOF ===-->
</CT_CodelistCatalogue>

```

The disadvantage of this approach is that it does not provide a URL for each individual CodeDefinition.
Therefore, we propose the alternative approach also, used by INSPIRE (See example Codelist at https://inspire.ec.europa.eu/metadata-codelist/DegreeOfConformity).  Items then have individual URI like this: https://inspire.ec.europa.eu/metadata-codelist/DegreeOfConformity/conformant.

For this example; values are then available in multiple formats (XML Registry, XML ISO 19135, RDF/XML, JSON etc.) at paths such as

https://inspire.ec.europa.eu/metadata-codelist/DegreeOfConformity/DegreeOfConformity.en.rdf

CEOS might publish a similar RDF/XML file...

E.g. `https://ceos.org/ard/metadata-codelists/PFS/PFS.rdf` document. 

```xml
<?xml version='1.0' encoding='utf-8'?>
<rdf:RDF xmlns:dcat="http://www.w3.org/ns/dcat#"  xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:rdfs="http://www.w3.org/2000/01/rdf-schema#" xmlns:owl="http://www.w3.org/2002/07/owl#" xmlns:skos="http://www.w3.org/2004/02/skos/core#" xmlns:dct="http://purl.org/dc/terms/">

    <rdf:Description rdf:about="https://ceos.org/ard/metadata-codelists/PFS">
      <dct:identifier>https://ceos.org/ard/metadata-codelists/PFS</dct:identifier>
      <skos:prefLabel xml:lang="en">Product Family Specification</skos:prefLabel>
   </rdf:Description>
   
   <rdf:Description rdf:about="https://ceos.org/ard/metadata-codelists/PFS/SR">
      <dct:identifier rdf:datatype="http://www.w3.org/2000/01/rdf-schema#Literal">https://ceos.org/ard/metadata-codelists/PFS/SR</dct:identifier>
      <rdf:type rdf:resource="http://www.w3.org/2004/02/skos/core#Concept"/>
      <skos:inScheme rdf:resource="https://ceos.org/ard/metadata-codelists/PFS"/>
      <skos:topConceptOf rdf:resource="https://ceos.org/ard/metadata-codelists/PFS"/>
      <dct:title xml:lang="en">Surface Reflectance</dct:title>
      <skos:prefLabel xml:lang="en">Surface Reflectance</skos:prefLabel>
      <skos:definition xml:lang="en">The Surface Reflectance Product Family ...</skos:definition>
      <skos:broader rdf:resource="https://ceos.org/ard/metadata-codelists/PFS"/>
   </rdf:Description>

</rdf:RDF>
```




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
			<gco:CharacterString>This collection is conformant with the CEOS-ARD Product Family Specification: Normalised Radar Backscatter</gco:CharacterString>
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
                 xmlns:gml="http://www.opengis.net/gml/3.2"
                 xmlns:gmx="http://www.isotc211.org/2005/gmx"
                 xmlns:srv="http://www.isotc211.org/2005/srv"
                 xmlns:xlink="http://www.w3.org/1999/xlink"
                 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
                 xsi:schemaLocation="http://www.isotc211.org/2005/gmi ./gmi/gmi.xsd">
                 
	<gmd:dataQualityInfo xmlns:gmd="http://www.isotc211.org/2005/gmd">
		<gmd:DQ_DataQuality>
			<gmd:scope>
				<gmd:DQ_Scope>
					<gmd:level>
						<gmd:MD_ScopeCode codeList="http://www.tc211.org/ISO19139/resources/codeList.xml#MD_ScopeCode" codeListValue="series"/>
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
												<gmd:CI_DateTypeCode codeList="https://standards.iso.org/iso/19139/resources/gmxCodelists.xml#CI_DateTypeCode" codeListValue="publication"/>
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

This section describes best practices for ISO 19115-3 {cite}`iso19115_3` collection metadata encoding.


> **Example: 2.1**  
>  Documenting conformance with specification or conformance class in ISO19115-3 metadata (with citation).


TBD:
- remove unnecessary namespaces.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<mdb:MD_Metadata xmlns:mdb="http://standards.iso.org/iso/19115/-3/mdb/1.0"
                 xmlns:cat="http://standards.iso.org/iso/19115/-3/cat/1.0"
                 xmlns:cit="http://standards.iso.org/iso/19115/-3/cit/1.0"
                 xmlns:gco="http://standards.iso.org/iso/19115/-3/gco/1.0"
                 xmlns:gcx="http://standards.iso.org/iso/19115/-3/gcx/1.0"
                 xmlns:gex="http://standards.iso.org/iso/19115/-3/gex/1.0"
                 xmlns:gml="http://www.opengis.net/gml"
                 xmlns:lan="http://standards.iso.org/iso/19115/-3/lan/1.0"
                 xmlns:mac="http://standards.iso.org/iso/19115/-3/mac/1.0"
                 xmlns:mas="http://standards.iso.org/iso/19115/-3/mas/1.0"
                 xmlns:mcc="http://standards.iso.org/iso/19115/-3/mcc/1.0"
                 xmlns:mco="http://standards.iso.org/iso/19115/-3/mco/1.0"
                 xmlns:mda="http://standards.iso.org/iso/19115/-3/mda/1.0"
                 xmlns:mdq="http://standards.iso.org/iso/19157/-2/mdq/1.0"
                 xmlns:mds="http://standards.iso.org/iso/19115/-3/mds/1.0"
                 xmlns:mdt="http://standards.iso.org/iso/19115/-3/mdt/1.0"
                 xmlns:mex="http://standards.iso.org/iso/19115/-3/mex/1.0"
                 xmlns:mmi="http://standards.iso.org/iso/19115/-3/mmi/1.0"
                 xmlns:mpc="http://standards.iso.org/iso/19115/-3/mpc/1.0"
                 xmlns:mrc="http://standards.iso.org/iso/19115/-3/mrc/1.0"
                 xmlns:mrd="http://standards.iso.org/iso/19115/-3/mrd/1.0"
                 xmlns:mri="http://standards.iso.org/iso/19115/-3/mri/1.0"
                 xmlns:mrl="http://standards.iso.org/iso/19115/-3/mrl/1.0"
                 xmlns:mrs="http://standards.iso.org/iso/19115/-3/mrs/1.0"
                 xmlns:msr="http://standards.iso.org/iso/19115/-3/msr/1.0"
                 xmlns:srv="http://standards.iso.org/iso/19115/-3/srv/2.0"
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
Collection metadata records in ISO19115-3 {cite}`iso19115_3` format should advertise conformance status with respect to CEOS-ARD PFS using a citation element with reference to the document URI or conformance class URI as shown in example 1.2. 
`````



> **Example: 2.2**  
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
												<cit:CI_DateTypeCode codeList="https://standards.iso.org/iso/19115/resources/Codelists/cat/codelists.xml#CI_DateTypeCode" codeListValue="publication"/>
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
												<cit:CI_OnLineFunctionCode codeList="http://standards.iso.org/ittf/PubliclyAvailableStandards/ISO_19139_Schemas/resources/codelist/ML_gmxCodelists.xml#CI_OnLineFunctionCode" codeListValue="information"/>
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
												<cit:CI_OnLineFunctionCode codeList="http://standards.iso.org/ittf/PubliclyAvailableStandards/ISO_19139_Schemas/resources/codelist/ML_gmxCodelists.xml#CI_OnLineFunctionCode" codeListValue="information"/>
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
												<cit:CI_OnLineFunctionCode codeList="http://standards.iso.org/ittf/PubliclyAvailableStandards/ISO_19139_Schemas/resources/codelist/ML_gmxCodelists.xml#CI_OnLineFunctionCode" codeListValue="information"/>
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
												<cit:CI_DateTypeCode codeList="https://standards.iso.org/iso/19115/resources/Codelists/cat/codelists.xml#CI_DateTypeCode" codeListValue="publication"/>
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


> **Example: 2.3**  
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

    - [novasar_l2ard_hh_hv.xml (short)](./examples/iso19115-3/novasar_l2ard_hh_hv_1.xml)
    - [novasar_l2ard_hh_hv.xml (long)](./examples/iso19115-3/novasar_l2ard_hh_hv_2.xml)


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
````


Alternatively, the lightweight approach with controlled keywords can be used.

> **Example: 4.2**  
>  Documenting conformance with specification in STAC collection {cite}`stac` metadata using the STAC CEOS-ARD Extension {cite}`stac_ceos_ard`.


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

TBD

> **Example: 5.1**  
>  Documenting conformance with specification or conformance class in DIF10 metadata.


### UMM-JSON Encoding

This section describes best practices for UMM-JSON {cite}`umm_json` collection metadata encoding.
TBD

> **Example: 6.1**  
>  Documenting conformance with specification or conformance class in UMM-JSON metadata.


### GeoDCAT-AP Encoding

This section describes best practices for GeoDCAT-AP {cite}`geodcat_ap` collection metadata encoding based on DCAT {cite}`dcat_v3`.
The proposed encoding is derived from the guidance in the https://github.com/GeoCat/iso-19139-to-dcat-ap/blob/master/documentation/Mappings.md#mapping-conformance-result[ISO19139 to DCAT-AP] mappings.

See also https://semiceu.github.io/GeoDCAT-AP/releases/3.0.0/#conformance-test-results

https://semiceu.github.io/GeoDCAT-AP/releases/3.0.0/#conformity-and-data-quality---not-in-iso19115-core

https://inspire.ec.europa.eu/metadata-codelist/DegreeOfConformity

example 38

```
prov:wasUsedBy [
  a prov:Activity;
# Conformity degree
  prov:generated [ a prov:Entity ;
    dct:type <http://inspire.ec.europa.eu/metadata-codelist/DegreeOfConformity/conformant> ;
    dct:description "See the referenced specification"@en
    prov:qualifiedAssociation [ a prov:Association ;
      prov:hadPlan [ a prov:Plan;
        prov:wasDerivedFrom [
# Specification
          a prov:Entity , dct:Standard ;
          dct:title "COMMISSION REGULATION (EC) No 976/2009 of 19 October 2009
          implementing Directive 2007/2/EC of the European Parliament and of the Council
          as regards the Network Services"@en
          dct:issued "2009-10-20"^^xsd:date
      ]
    ];
  ];
] .
```



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

Possible values are:

- TBD
- http://inspire.ec.europa.eu/metadata-codelist/DegreeOfConformity/conformant
- TBD

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

`````{admonition} CEOS-ARDMD-REC-7010 [Recommendation]
:class: tip
Collection metadata records in GeoDCAT-AP {cite}`geodcat_ap` format (in RDF/XML, Turtle or JSON-LD serialisation) should advertise conformance status with respect to CEOS-ARD PFS using a citation element with dct:title and reference to the document URI or conformance class URI (rdf:Description) as shown in example 7.3. 
`````

### OGC 17-084r1 Encoding

This section describes best practices for OGC 17-084r1 {cite}`OGC_17_084r1` collection metadata encoding.

TBD


> **Example: 8.1**  
>  Documenting conformance with specification or conformance class in OGC 17-084r1 {cite}`OGC_17_084r1` metadata.



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




## Traceability

TBD: mapping of proposed requirements to source documents and metadata formats.