### This file documents the tests that are currently failing (and thus being skipped by the Postman collection runner) and the reason why these tests fail.

ZRC:
- **zrc-001g** until **zrc-001i**: resource validation on `zaaktype`-url for `Zaak` not yet implemented
- **zrc-003b**: Adding duplicate informatieobject under `<zaak_url>/informatieobjecten` on localhost (one will use localhost in url and the other 127.0.0.1)
- **zrc-003c**: `ObjectInformatieObject` deletion does not cascade from DRC to ZRC, causing the `ObjectInformatieObject` to not be deleted from DRC ([Issue #909](https://github.com/VNG-Realisatie/gemma-zaken/issues/909))
- **zrc-004a**: `zaak_list` returns `Zaak`en with `zaaktype`s that are not part of the zaaktypes_claim in the JWT token  
- **zrc-004b**: `zaak__zoek` returns `Zaak`en with `zaaktype`s that are not part of the zaaktypes_claim in the JWT token  
- **zrc-004c**: `zaak_detail` returns `Zaak`en with `zaaktype`s that are not part of the zaaktypes_claim in the JWT token  
- **zrc-008d** until **zrc-008f**: creating/updating/partially updating `Zaak` with a valid url that points to another `Zaak` throws 412 instead of 201/200
- **zrc-009c**: partially updating a `Zaak` with `opschorting` with invalid structure results in 200 instead of 400, changing the value of `opschorting` to `{indicatie: false, reden: ""}`
- **zrc-009f**: partially updating a `Zaak` with `verlenging` with invalid structure results in 200 instead of 400, changing the value of `opschorting` to `{reden: "", duur: null}`
- **zrc-011a**: creating a `Zaak` with `betalingsindicatie` set to `nvt` and with a value that is not `null` for `laatsteBetaalDatum` results in 201 instead of 400
- **zrc-013g**: missing appropriate `selectielijstklasse` in https://ref.tst.vng.cloud/referentielijsten/api/v1/resultaten for `afleidingswijze_brondatum` `ander_datumkenmerk` 
- **zrc-015h**: same issue as **zrc-003c**

DRC:
- **drc-001g** until **drc-001i**: resource validation on `informatieobjecttype`-url for `EnkelvoudigInformatieObject` not yet implemented
- **drc-002g**: resource validation on `object`-url for `ObjectInformatieObject` with `objecttype` set to `zaak` not yet implemented
- **drc-002h**: resource validation on `object`-url for `ObjectInformatieObject` with `objecttype` set to `besluit` not yet implemented
- **drc-003b**: `ObjectInformatieObject` deletion does not cascade from DRC to BRC, causing the `ObjectInformatieObject` to not be deleted from DRC
- **drc-003d**: partially updating `ObjectInformatieObject` while `objectType` is set to `besluit` with values for `titel`, `beschrijving`, `registratiedatum` sets these values in the `ObjectInformatieObject`, instead of ignoring them
- **drc-003e**: updating `ObjectInformatieObject` with a different value for `aardRelatieWeergave` should not be possible, but the API does not use the given value for `aardRelatieWeergave`, causing the result to be 200 without any values actually changing
- **drc-003f**: partially updating `ObjectInformatieObject` with a different value for `aardRelatieWeergave` should not be possible, but the API does not use the given value for `aardRelatieWeergave`, causing the result to be 200 without any values actually changing
- **drc-004a**: same issue as **drc-003b**
- **drc-004b**: similar to **zrc-003b**, `informatieobject`-url is saved using 127.0.0.1 instead of localhost under `<besluit_url>/informatieobjecten`
- **drc-005a**: updating `EnkelvoudigInformatieObject` with `status` set to `in_bewerking` and `verzenddatum` set to not `null` results in 200 instead of 400
- **drc-005b**: partially updating `EnkelvoudigInformatieObject` with `verzenddatum` set to not `null` while `status` was already set to `in_bewerking` results in 200 instead of 400
- **drc-005c**: updating `EnkelvoudigInformatieObject` with `status` set to `ter_vaststelling` and `verzenddatum` set to not `null` results in 200 instead of 400
- **drc-005d**: partially updating `EnkelvoudigInformatieObject` with `verzenddatum` set to not `null` while `status` was already set to `ter_vaststelling` results in 200 instead of 400

BRC:
- **brc-001g** until **brc-001i**: resource validation on `besluittype`-url for `Besluit` not yet implemented
- **brc-003b**: same issue as **zrc-003b**
- **brc-003c**: same issue as **drc-003b**
