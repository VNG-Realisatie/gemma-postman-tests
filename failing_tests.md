### This file documents the tests that are currently failing (and thus being skipped by the Postman collection runner) and the reason why these tests fail.

ZRC:
- **zrc-001g** until **zrc-001i**: resource validation on `zaaktype`-url for `Zaak` not yet implemented
- **zrc-002b-c**: when updating identificatie gives `wijzigen-niet-toelaten`
- **zrc-006a**: `zaak_list` returns `Zaak`en with `zaaktype`s that are not part of the zaaktypes_claim in the JWT token  
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