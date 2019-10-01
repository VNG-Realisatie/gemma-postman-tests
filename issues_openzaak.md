# Issues in OpenZaak:

## Catalogi:
- Resultaattype validation not yet implemented (has been implemented in reference components, see: https://github.com/VNG-Realisatie/gemma-zaaktypecatalogus/pull/62)
- Creating a Zaaktype-Informatieobjecttype relatie does not add the Informatieobjecttype to Zaaktype.informatieobjecttypen
- Creating Zaaktype with urls in besluittypen and then creating a Besluit with a Zaak gives zaaktype-mismatch

## Zaken:
- ZaakInformatieObject with invalid zaak-url or informatieobject-url gives 500 error instead of 400
- Zaak deleten moet zonder header

## All:
- Titles of API specs are all 'ZAKEN API', even for catalogi, documenten and besluiten
- Trying to perform an operation with an application without the required scope gives 403 not_authenticated instead of 403 permission_denied (should be fixed by vng_api_common==1.0.12)