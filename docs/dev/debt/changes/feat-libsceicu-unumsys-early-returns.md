# libSceIcu

## add Functional

- [ICU numbering system exports](../../../core/libs/prx/libSceIcu/NumberingSystem.cpp) follow ICU 68.2 [unumsys.cpp](https://github.com/unicode-org/icu/blob/84e1f26ea77152936e70d53178a816dbfbf69989/icu4c/source/i18n/unumsys.cpp): `unumsys_openAvailableNames` (47-52) returns null for a failing `UErrorCode` (above zero) with the status untouched; `unumsys_getName` (55-59) and `unumsys_isAlgorithmic` (69-73) have no early return, so they have their prototypes and throw for every input. Every path that needs `UNumberingSystem` objects throws `NotImplemented_nid_no_patch`. Unverified on a console. Closes when: those are implemented and compared with the console.
