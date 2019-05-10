---
title: Struktury a sjednocení | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- structures [Visual Studio SDK]
ms.assetid: 9ff0a8f8-1ee6-4fdd-8b80-206436ff589b
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7522e1c00598574e46e1f23622f0e051fcfb2c4e
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/09/2019
ms.locfileid: "65460871"
---
# <a name="structures-and-unions"></a>Struktury a sjednocení
Níže jsou struktury a sjednocení v aplikaci Visual Studio SDK ladění.

- [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md) Určuje ID procesu, který může být ID systému nebo identifikátor GUID.

- [BP_CONDITION](../../../extensibility/debugger/reference/bp-condition.md) popisuje podmínky, za kterých bude platit zarážku.

- [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md) popisuje řešení k chybě zarážku, včetně umístění, aplikace a vlákna.

- [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md) Určuje typ struktury, na které se používají k popisu umístění zarážky.

- [BP_LOCATION_CODE_ADDRESS](../../../extensibility/debugger/reference/bp-location-code-address.md) definuje součásti, které popisují umístění zarážky na adrese v kódu.

- [BP_LOCATION_CODE_CONTEXT](../../../extensibility/debugger/reference/bp-location-code-context.md) popisuje umístění zarážky, který je vázán přímo na adresu v programu, který se právě ladí.

- [BP_LOCATION_CODE_FILE_LINE](../../../extensibility/debugger/reference/bp-location-code-file-line.md) popisuje umístění zarážky na řádku ve zdrojovém souboru kódu.

- [BP_LOCATION_CODE_FUNC_OFFSET](../../../extensibility/debugger/reference/bp-location-code-func-offset.md) popisuje posunu umístění zarážky na funkci v kódu.

- [BP_LOCATION_CODE_STRING](../../../extensibility/debugger/reference/bp-location-code-string.md) používá k nastavení kódu zarážky založené na řetězec, který může uživatel zadat z integrovaného vývojového prostředí.

- [BP_LOCATION_DATA_STRING](../../../extensibility/debugger/reference/bp-location-data-string.md) používá k nastavení datové zarážky, které jsou založeny na řetězec, který může uživatel zadat z integrovaného vývojového prostředí.

- [BP_LOCATION_RESOLUTION](../../../extensibility/debugger/reference/bp-location-resolution.md) popisuje řešení zarážky v konkrétním umístění.

- [BP_PASSCOUNT](../../../extensibility/debugger/reference/bp-passcount.md) popisuje počet a podmínky, na kterých bude vyvoláno zarážku po s dřív Bezproblémová.

- [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) obsahuje informace potřebné k implementaci zarážku.

- [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) obsahuje informace potřebné k implementaci zarážky (stejné jako [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) struktura zahrnuje ale identifikátor GUID, omezení a zarážky s trasováním informace dodavatele).

- [BP_RESOLUTION_CODE](../../../extensibility/debugger/reference/bp-resolution-code.md) popisuje umístění zarážky kódu.

- [BP_RESOLUTION_DATA](../../../extensibility/debugger/reference/bp-resolution-data.md) popisuje výsledek vazby datové zarážky.

- [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md) popisuje informace o vázaná zarážka kódu zarážku nebo zarážku data.

- [BP_RESOLUTION_LOCATION](../../../extensibility/debugger/reference/bp-resolution-location.md) určuje strukturu řešení umístění zarážky.

- [BSTR_ARRAY](../../../extensibility/debugger/reference/bstr-array.md) popisuje pole řetězců.

- [BUILT_TYPE](../../../extensibility/debugger/reference/built-type.md) Určuje informace o typ pole z metadat.

- [CODE_PATH](../../../extensibility/debugger/reference/code-path.md) popisuje volání funkce nebo metody.

- [COMPUTER_INFO](../../../extensibility/debugger/reference/computer-info.md) popisuje počítače, na kterém je spuštěný ladicí program.

- [CONST_GUID_ARRAY](../../../extensibility/debugger/reference/const-guid-array.md) popisuje seznamu identifikátorů GUID.

- [CONTEXT_INFO](../../../extensibility/debugger/reference/context-info.md) popisuje místní paměti nebo kontext kódu.

- [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md) popisuje adresu v programu, který se právě ladí.

- [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md) představuje jeden z několika různých druhů adresy.

- [DEBUG_CUSTOM_VIEWER](../../../extensibility/debugger/reference/debug-custom-viewer.md) určuje vlastní prohlížeč nebo vizualizér typů.

- [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md) popisuje vlastnost, která ladění pak popisuje objekt hierarchickou povahu, který má název, typ a hodnotu.

- [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) popisuje odkaz.

- [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md) popisuje zpětný překlad do integrovaného vývojového prostředí pro zobrazení.

- [EXCEPTION_INFO](../../../extensibility/debugger/reference/exception-info.md) popisuje chybu výjimky nebo za běhu vyvolané laděnému programu.

- [FIELD_INFO](../../../extensibility/debugger/reference/field-info.md) popisuje místní proměnná, parametr nebo jiné pole.

- [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) popisuje rámec zásobníku.

- [GUID_ARRAY](../../../extensibility/debugger/reference/guid-array.md) popisuje celou řadu jedinečné identifikátory pro dostupné ladicí stroj.

- [JMC_CODE_SPEC](../../../extensibility/debugger/reference/jmc-code-spec.md) použít k nastavení JustMyCode informace pro modul.

- [MACHINE_INFO](../../../extensibility/debugger/reference/machine-info.md) popisuje konkrétní počítač.

- [METADATA_ADDRESS_ARRAYELEM](../../../extensibility/debugger/reference/metadata-address-arrayelem.md) popisuje k elementu pole v rámci pole.

- [METADATA_ADDRESS_FIELD](../../../extensibility/debugger/reference/metadata-address-field.md) popisuje adresy pole třídy nebo struktury.

- [METADATA_ADDRESS_LOCAL](../../../extensibility/debugger/reference/metadata-address-local.md) popisuje adresu místní proměnné v rámci oboru (obvykle funkce nebo metoda).

- [METADATA_ADDRESS_METHOD](../../../extensibility/debugger/reference/metadata-address-method.md) popisuje adresu metody třídy.

- [METADATA_ADDRESS_PARAM](../../../extensibility/debugger/reference/metadata-address-param.md) popisuje parametr metody nebo funkce.

- [METADATA_ADDRESS_RETVAL](../../../extensibility/debugger/reference/metadata-address-retval.md) popisuje návratovou hodnotu z metody nebo funkce.

- [METADATA_TYPE](../../../extensibility/debugger/reference/metadata-type.md) popisuje typ pole z metadat.

- [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md) popisuje konkrétního modulu (knihovny DLL, EXE nebo sestavení).

- [MODULE_SYMBOL_SEARCH_INFO](../../../extensibility/debugger/reference/module-symbol-search-info.md) popisuje informace o vyhledávací cesty symbolů, které byly prohledány stavu.

- [NATIVE_ADDRESS](../../../extensibility/debugger/reference/native-address.md) popisuje nativní adresu.

- [PDB_TYPE](../../../extensibility/debugger/reference/pdb-type.md) popisuje typ pole z symbolů ze souboru PDB.

- [PENDING_BP_STATE_INFO](../../../extensibility/debugger/reference/pending-bp-state-info.md) popisuje stav zarážky, která jsou připravená k vytvoření vazby na místa v kódu.

- [PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md) popisuje proces.

- [PROGRAM_NODE_ARRAY](../../../extensibility/debugger/reference/program-node-array.md) popisuje seznam [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) objekty, které představují uzly programů.

- [PROVIDER_PROCESS_DATA](../../../extensibility/debugger/reference/provider-process-data.md) popisuje procesy spuštěné na počítači.

- [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md) popisuje umístění řádku a sloupci v zadaném textu.

- [THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md) popisuje vlastnosti vlákno.

- [TYPE_INFO](../../../extensibility/debugger/reference/type-info.md) popisuje typ pole.

- [UNMANAGED_ADDRESS_PHYSICAL](../../../extensibility/debugger/reference/unmanaged-address-physical.md) popisuje fyzickou adresu.

- [UNMANAGED_ADDRESS_THIS_RELATIVE](../../../extensibility/debugger/reference/unmanaged-address-this-relative.md) popisuje adresu, která je vzhledem k `this` ukazatel (`Me` v jazyce Visual Basic).

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h sh.h či ee.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Referenční dokumentace ke knihovně API](../../../extensibility/debugger/reference/api-reference-visual-studio-debugging.md)