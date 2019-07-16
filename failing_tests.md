### This file documents the tests that are currently failing (and thus being skipped by the Postman collection runner) and the reason why these tests fail.

## Failing tests:

ZRC:
- **zrc-001g** until **zrc-001i**: resource validation on `zaaktype`-url for `Zaak` not yet implemented

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
