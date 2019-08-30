### This file documents the tests that are currently failing (and thus being skipped by the Postman collection runner) and the reason why these tests fail.

## Failing tests:

ZRC:
- **zrc-001g** until **zrc-001i**: resource validation on `zaaktype`-url for `Zaak` not yet implemented
- **zrc-002b-c**: when updating identificatie gives `wijzigen-niet-toelaten` 
- **zrc-006b**: `zaak__zoek` returns `Zaak`en with `zaaktype`s that are not part of the zaaktypes_claim in the JWT token  
- **zrc-006c**: `zaak_detail` returns `Zaak`en with `zaaktype`s that are not part of the zaaktypes_claim in the JWT token
- **zrc-007c-d**: (partially) updating a closed `Zaak` without the required scopes should give 403 but gives 200, probably due to changes to authorizations
- **zrc-011c&f**: partially updating a `Zaak` with a `GegevensGroep` (`opschorting`/`verlenging`) with invalid structure should list all the fields that are missing ([Issue #1026](https://github.com/VNG-Realisatie/gemma-zaken/issues/1026))
- **zrc-015g**: missing appropriate `selectielijstklasse` in https://ref.tst.vng.cloud/referentielijsten/api/v1/resultaten for `afleidingswijze_brondatum` `ander_datumkenmerk`

DRC:
- **drc-001g**: resource validation on `informatieobjecttype`-url for `EnkelvoudigInformatieObject` fails on schema fetch for certain urls
- **drc-001h-i**: resource validation on `informatieobjecttype`-url for `EnkelvoudigInformatieObject` seems to not be applied for PUT/PATCH
- **drc-002c**: resource validation on `object`-url for `ObjectInformatieObject` with `objecttype` set to `zaak` not yet implemented
- **drc-002d**: resource validation on `object`-url for `ObjectInformatieObject` with `objecttype` set to `besluit` not yet implemented

BRC:
- **brc-001g** until **brc-001i**: resource validation on `besluittype`-url for `Besluit` not yet implemented
- **brc-004a** until **brc-004c**: BesluitInformatieObject does not have a field `aardRelatie` or `aardRelatieWeergave`

ZTC:
- **ztc-001b**: no resource validation for `selectielijstProcestype` on `Zaaktype`
- **ztc-002c** and **ztc-002d**: creating Resultaattype with selectielijstklasse url that does not point to correct resource throws 500
- **ztc-002e**: no validation to check if Resultaattype.selectielijstklasse.procestype == Resultaattype.zaaktype.selectielijstProcestype
- **ztc-002g**: Resultaat.archiefactietermijn not derived from Resultaat.bewaartermijn if not defined

## Incomplete tests:

ZRC:
- **zrc-015**: cannot test all values for `afleidingswijze` for archiving, because it is dependent on **ztc-003** - **ztc-008**, which is incomplete

ZTC:
- **ztc-003** onward: incomplete
