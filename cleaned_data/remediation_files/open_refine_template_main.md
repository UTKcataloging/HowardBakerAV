# OpenRefine Template for Howard Baker Audiovisual Collection (Main Object)

---

## Prefix

```
<?xml version="1.0" encoding="UTF-8"?>
<modsCollection xmlns="http://www.loc.gov/mods/v3" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xlink="http://www.w3.org/1999/xlink" xsi:schemaLocation="http://www.loc.gov/mods/v3 http://www.loc.gov/standards/mods/v3/mods-3-5.xsd">
```

## Row Template

```
<mods>
<identifier type="local">{{cells['adminDB'].value}}</identifier>
{{if(isBlank(cells['title'].value), '', '<titleInfo><title>' + cells["title"].value + '</title></titleInfo>')}} {{if(isBlank(cells['supplied_title'].value), '', '<titleInfo supplied="yes"><title>' + cells['supplied_title'].value + '</title></titleInfo>')}}
{{if(isBlank(cells["abstract"].value),'', '<abstract>' + cells['abstract'].value + '</abstract>')}}
{{'<originInfo>' + if(isBlank(cells['date'].value), '', '<dateCreated>' + cells['date'].value + '</dateCreated>') + if(isBlank(cells['date_edtf'].value), '', '<dateCreated encoding="edtf" keyDate="yes">' + cells['date_edtf'].value + '</dateCreated>') + if(isBlank(cells['date_range'].value), '', '<dateCreated encoding="edtf" point="start" keyDate="yes">' + cells['date_range'].value + '</dateCreated>') + if(isBlank(cells['date_range_end'].value), '', '<dateCreated encoding="edtf" point="end">' + cells['date_range_end'].value + '</dateCreated>') + '</originInfo>'}}
<physicalDescription><form authority="aat" valueURI="{{cells['format_broad_URI'].value}}">{{cells['format_broad'].value}}</form>
{{if(isBlank(cells['form_aat'].value), '', '<form authority="aat" valueURI="' + cells['form_aat_URI'].value + '">' + cells['form_aat'].value + '</form>')}}
{{if(isBlank(cells['form_aat2'].value), '', '<form authority="aat" valueURI="' + cells['form_aat2_URI'].value + '">' + cells['form_aat2'].value + '</form>')}}
<extent>{{cells['time'].value}}</extent></physicalDescription>
{{if(isBlank(cells['note'].value), '', '<note>' + cells['note'].value + '</note>')}}
{{if(isBlank(cells['note2'].value), '', '<note>' + cells['note2'].value + '</note>')}}
{{if(isBlank(cells['note3'].value), '', '<note>' + cells['note3'].value + '</note>')}}
{{if(isBlank(cells['subject'].value), '', '<subject authority="lcsh" valueURI="' + cells['subject_URI'].value + '"><topic>' + cells['subject'].value + '</topic></subject>')}}
{{if(isBlank(cells['subject2'].value), '', '<subject authority="lcsh" valueURI="' + cells['subject2_URI'].value + '"><topic>' + cells['subject2'].value + '</topic></subject>')}}
{{if(isBlank(cells['subject3'].value), '', '<subject authority="lcsh" valueURI="' + cells['subject3_URI'].value + '"><topic>' + cells['subject3'].value + '</topic></subject>')}}
{{if(isBlank(cells['subject_name'].value), '', '<subject authority="naf" valueURI="' + cells['subject_name_URI'].value + '"><name><namePart>' + cells['subject_name'].value + '</namePart></name></subject>')}}
{{if(isBlank(cells['subject_name_2'].value), '', '<subject authority="naf" valueURI="' + cells['subject_name_2_URI'].value + '"><name><namePart>' + cells['subject_name_2'].value + '</namePart></name></subject>')}}
<language><languageTerm type="text" authority="iso639-2b">{{cells['language'].value}}</languageTerm></language>
<typeOfResource>{{cells['typeOfResource'].value}}</typeOfResource>
{{if(isBlank(cells['typeOfResource2'].value), '', '<typeOfResource>' + cells['typeOfResource2'].value + '</typeOfResource>')}}
<relatedItem displayLabel="Project" type="host"><titleInfo><title>Howard Baker Audiovisual Materials</title></titleInfo></relatedItem>
<relatedItem displayLabel="Collection" type="host"><titleInfo><title>{{cells['archival_collection'].value}}</title></titleInfo><identifier>{{cells['collection_identifier'].value}}</identifier></relatedItem>
<location><physicalLocation valueURI="http://id.loc.gov/authorities/names/no2006129900">Howard H. Baker Jr. Center for Public Policy</physicalLocation></location>
<recordInfo><recordContentSource valueURI="http://id.loc.gov/authorities/names/n87808088">University of Tennessee, Knoxville. Libraries</recordContentSource></recordInfo>
<accessCondition type="use and reproduction" xlink:href="{{cells['rights_URI'].value}}">{{cells['rights'].value}}</accessCondition>
</mods>
```

## Row Separator

**LEAVE BLANK**

## Suffix

```
</modsCollection>
```