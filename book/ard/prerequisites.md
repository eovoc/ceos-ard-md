# Prerequisites


The guidelines can be applied to the various flavours of metadata specifications covered in the remainder of this document.

To apply the above high level requirements, the following information related to CEOS specifications or more precisely CEOS-ARD Product Family specifications should be agreed:

- Document citations, including precise title, date and document identifier (URI)
- Conformance class identifiers (URI) - when used in future specifications.

## Requirements for Citations

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

## Requirements for Keywords

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

For this example, values are then available in multiple formats (XML Registry, XML ISO 19135, RDF/XML, JSON etc.) at paths such as

https://inspire.ec.europa.eu/metadata-codelist/DegreeOfConformity/DegreeOfConformity.en.rdf

CEOS might publish a similar RDF/XML file with the required SKOS concepts...

E.g. `https://ceos.org/ard/metadata-codelists/PFS/PFS.rdf` document. 

```xml
<?xml version='1.0' encoding='utf-8'?>
<rdf:RDF xmlns:dcat="http://www.w3.org/ns/dcat#"
         xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xmlns:rdfs="http://www.w3.org/2000/01/rdf-schema#"
         xmlns:owl="http://www.w3.org/2002/07/owl#"
         xmlns:skos="http://www.w3.org/2004/02/skos/core#"
         xmlns:dct="http://purl.org/dc/terms/">

	<rdf:Description rdf:about="https://ceos.org/ard/metadata-codelists/PFS">
		<skos:prefLabel xml:lang="en">Product Family Specification</skos:prefLabel>
	</rdf:Description>

	<rdf:Description rdf:about="https://ceos.org/ard/metadata-codelists/PFS/SR">
		<rdf:type rdf:resource="http://www.w3.org/2004/02/skos/core#Concept"/>
		<skos:inScheme rdf:resource="https://ceos.org/ard/metadata-codelists/PFS"/>
		<skos:topConceptOf rdf:resource="https://ceos.org/ard/metadata-codelists/PFS"/>
		<skos:prefLabel xml:lang="en">Surface Reflectance</skos:prefLabel>
		<skos:definition xml:lang="en">The Surface Reflectance Product Family ...</skos:definition>
		<skos:broader rdf:resource="https://ceos.org/ard/metadata-codelists/PFS"/>
	</rdf:Description>

    <rdf:Description rdf:about="https://ceos.org/ard/metadata-codelists/PFS/NRB">
		<rdf:type rdf:resource="http://www.w3.org/2004/02/skos/core#Concept"/>
		<skos:inScheme rdf:resource="https://ceos.org/ard/metadata-codelists/PFS"/>
		<skos:topConceptOf rdf:resource="https://ceos.org/ard/metadata-codelists/PFS"/>
		<skos:prefLabel xml:lang="en">Normalised Radar Backscatter</skos:prefLabel>
		<skos:definition xml:lang="en">The SNormalised Radar Backscatter Family ...</skos:definition>
		<skos:broader rdf:resource="https://ceos.org/ard/metadata-codelists/PFS"/>
	</rdf:Description>
</rdf:RDF>
```

