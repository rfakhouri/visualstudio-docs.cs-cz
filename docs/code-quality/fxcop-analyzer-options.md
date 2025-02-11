---
title: Možnosti konfigurace analyzátor FxCop
ms.date: 03/11/2019
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 3c7050cbb80b1b79009a23a2d9bfedc40204fede
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62816711"
---
# <a name="configuration-options-for-fxcop-analyzers"></a>Možnosti konfigurace pro analyzátory FxCop

Tato stránka obsahuje seznam dostupných možností konfigurace, jejich povolené hodnoty a konfigurovat pravidla pro jednotlivé možnosti.

## <a name="apisurface"></a>api_surface

| Popis | Povolené hodnoty | Výchozí hodnota | Konfigurovat pravidla |
| - | - | - | - |
| Které části plochy rozhraní API pro analýzu | `public`<br/>`internal` Nebo `friend`<br/>`private`<br/>`all`<br/><br/>Více hodnot oddělte čárkou () | `public` | [CA1000](ca1000-do-not-declare-static-members-on-generic-types.md)<br/>[CA1003](ca1003-use-generic-event-handler-instances.md)<br/>[CA1008](ca1008-enums-should-have-zero-value.md)<br/>[CA1010](ca1010-collections-should-implement-generic-interface.md)<br/>[CA1012](ca1012-abstract-types-should-not-have-constructors.md)<br/>[CA1024](ca1024-use-properties-where-appropriate.md)<br/>[CA1027](ca1027-mark-enums-with-flagsattribute.md)<br/>[CA1028](ca1028-enum-storage-should-be-int32.md)<br/>[CA1030](ca1030-use-events-where-appropriate.md)<br/>[CA1036](ca1036-override-methods-on-comparable-types.md)<br/>[CA1040](ca1040-avoid-empty-interfaces.md)<br/>[CA1041](ca1041-provide-obsoleteattribute-message.md)<br/>[CA1043](ca1043-use-integral-or-string-argument-for-indexers.md)<br/>[CA1044](ca1044-properties-should-not-be-write-only.md)<br/>[CA1051](ca1051-do-not-declare-visible-instance-fields.md)<br/>[CA1052](ca1052-static-holder-types-should-be-sealed.md)<br/>[CA1054](ca1054-uri-parameters-should-not-be-strings.md)<br/>[CA1055](ca1055-uri-return-values-should-not-be-strings.md)<br/>[CA1056](ca1056-uri-properties-should-not-be-strings.md)<br/>[CA1058](ca1058-types-should-not-extend-certain-base-types.md)<br/>[CA1063](ca1063-implement-idisposable-correctly.md)<br/>[CA1708](ca1708-identifiers-should-differ-by-more-than-case.md)<br/>[CA1710](ca1710-identifiers-should-have-correct-suffix.md)<br/>[CA1711](ca1711-identifiers-should-not-have-incorrect-suffix.md)<br/>[CA1714](ca1714-flags-enums-should-have-plural-names.md)<br/>[CA1715](ca1715-identifiers-should-have-correct-prefix.md)<br/>[CA1716](ca1716-identifiers-should-not-match-keywords.md)<br/>[CA1717](ca1717-only-flagsattribute-enums-should-have-plural-names.md)<br/>[CA1720](ca1720-identifiers-should-not-contain-type-names.md)<br/>[CA1721](ca1721-property-names-should-not-match-get-methods.md)<br/>[CA1725](ca1725-parameter-names-should-match-base-declaration.md)<br/>[CA1802](ca1802-use-literals-where-appropriate.md)<br/>[CA1815](ca1815-override-equals-and-operator-equals-on-value-types.md)<br/>[CA1819](ca1819-properties-should-not-return-arrays.md)<br/>[CA2217](ca2217-do-not-mark-enums-with-flagsattribute.md)<br/>[CA2225](ca2225-operator-overloads-have-named-alternates.md)<br/>[CA2226](ca2226-operators-should-have-symmetrical-overloads.md)<br/>[CA2231](ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)<br/>[CA2234](ca2234-pass-system-uri-objects-instead-of-strings.md) |

## <a name="excludeasyncvoidmethods"></a>exclude_async_void_methods

| Popis | Povolené hodnoty | Výchozí hodnota | Konfigurovat pravidla |
| - | - | - | - |
| Jestli se má ignorovat asynchronní metody, které nevracejí hodnotu | `true`<br/>`false` | `false` | [CA2007](ca2007-do-not-directly-await-task.md) |

> [!NOTE]
> Ve verzi 2.6.3 a dříve balíčku analyzátor označovala jako tato možnost `skip_async_void_methods`.

## <a name="excludesinglelettertypeparameters"></a>exclude_single_letter_type_parameters

| Popis | Povolené hodnoty | Výchozí hodnota | Konfigurovat pravidla |
| - | - | - | - |
| Jestli se mají vyloučit jedním znakem [parametry typu](/dotnet/csharp/programming-guide/generics/generic-type-parameters) z pravidla, například `S` v `Collection<S>` | `true`<br/>`false` | `false` | [CA1715](ca1715-identifiers-should-have-correct-prefix.md) |

> [!NOTE]
> Ve verzi 2.6.3 a dříve balíčku analyzátor označovala jako tato možnost `allow_single_letter_type_parameters`.

## <a name="outputkind"></a>output_kind

| Popis | Povolené hodnoty | Výchozí hodnota | Konfigurovat pravidla |
| - | - | - | - |
| Určuje, že by měl být analyzován kód v projektu, který generuje tento typ sestavení | Jeden nebo více polí <xref:Microsoft.CodeAnalysis.OutputKind> výčet<br/><br/>Více hodnot oddělte čárkou () | Veškerý výstup typy | [CA2007](ca2007-do-not-directly-await-task.md) |