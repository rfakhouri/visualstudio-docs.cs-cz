---
title: Sada pravidel Rozšířená pravidla pokynů návrhu pro spravovaný kód
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: a338caf2-b75d-4f23-a0f9-3024fa0bceac
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: b2270caa0cf7db230fa030cb620d51f1677d9dec
ms.sourcegitcommit: b83fefa8177c5554cbe2c59c4d102cbc534f7cc6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/19/2019
ms.locfileid: "69585078"
---
# <a name="extended-design-guidelines-rules-rule-set-for-managed-code"></a>Sada pravidel Rozšířená pravidla pokynů návrhu pro spravovaný kód

Sada pravidel Rozšířená pravidla obecných zásad návrhu se rozšiřuje na základní pravidla obecných zásad návrhu, která maximalizují možnosti použitelnosti a udržovatelnosti, které jsou hlášeny. Dodatečné zdůraznění se řídí pokyny pro pojmenování. Měli byste zvážit zahrnutí této sady pravidel, pokud váš projekt obsahuje kód knihovny nebo pokud chcete vymáhat nejvyšší standardy pro psaní kódu, který se snadno udržuje.

Rozšířená pravidla obecných zásad návrhu zahrnují všechna pravidla v sadě pravidel [základní pravidla návrhu návrhu](../code-quality/basic-design-guideline-rules-rule-set-for-managed-code.md) , která zahrnují pravidla uvedená v sadě pravidel [spravovaná doporučená pravidla](../code-quality/managed-recommended-rules-rule-set-for-managed-code.md) .

V následující tabulce jsou popsána všechna pravidla v sadě pravidel Rozšířená pravidla obecných zásad návrhu společnosti Microsoft.

|Pravidlo|Popis|
|----------|-----------------|
|[CA1001](../code-quality/ca1001-types-that-own-disposable-fields-should-be-disposable.md)|Typy, které vlastní uvolnitelné pole, by měly být uvolnitelné|
|[CA1009](../code-quality/ca1009-declare-event-handlers-correctly.md)|Deklarujte správně obslužné rutiny událostí|
|[CA1016](../code-quality/ca1016-mark-assemblies-with-assemblyversionattribute.md)|Označte sestavení pomocí AssemblyVersionAttribute|
|[CA1033](../code-quality/ca1033-interface-methods-should-be-callable-by-child-types.md)|Metody rozhraní by měly být volatelné podřízenými typy|
|[CA1049](../code-quality/ca1049-types-that-own-native-resources-should-be-disposable.md)|Typy, které vlastní nativní prostředky, by měly být uvolnitelné|
|[CA1060](../code-quality/ca1060-move-p-invokes-to-nativemethods-class.md)|Přesuňte volání nespravovaných kódů do třídy NativeMethods|
|[CA1061](../code-quality/ca1061-do-not-hide-base-class-methods.md)|Neskrývejte metody základní třídy|
|[CA1063](../code-quality/ca1063-implement-idisposable-correctly.md)|Implementuje správně IDisposable|
|[CA1065](../code-quality/ca1065-do-not-raise-exceptions-in-unexpected-locations.md)|Nevyvolávejte výjimky v neočekávaných umístěních|
|[CA1301](../code-quality/ca1301-avoid-duplicate-accelerators.md)|Vyhněte se duplicitním akcelerátorům|
|[CA1400](../code-quality/ca1400-p-invoke-entry-points-should-exist.md)|Vstupní body volání nespravovaného kódu by měly existovat|
|[CA1401](../code-quality/ca1401-p-invokes-should-not-be-visible.md)|Volání nespravovaných kódů by neměla být viditelná|
|[CA1403](../code-quality/ca1403-auto-layout-types-should-not-be-com-visible.md)|Typy automatického rozložení by neměly být viditelné modelu COM|
|[CA1404](../code-quality/ca1404-call-getlasterror-immediately-after-p-invoke.md)|Volejte GetLastError ihned po volání nespravovaného kódu|
|[CA1405](../code-quality/ca1405-com-visible-type-base-types-should-be-com-visible.md)|Základní typy viditelného typu modelu COM by měly být viditelné modelu COM|
|[CA1410](../code-quality/ca1410-com-registration-methods-should-be-matched.md)|Metody registrace modelu COM by si měly odpovídat|
|[CA1415](../code-quality/ca1415-declare-p-invokes-correctly.md)|Deklarujte správně volání nespravovaných kódů|
|[CA1821](../code-quality/ca1821-remove-empty-finalizers.md)|Odeberte prázdné finalizační metody|
|[CA1900](../code-quality/ca1900-value-type-fields-should-be-portable.md)|Pole typů hodnot by měla být přenosná|
|[CA1901](../code-quality/ca1901-p-invoke-declarations-should-be-portable.md)|Deklarace volání nespravovaného kódu by měla být přenosná|
|[CA2002](../code-quality/ca2002-do-not-lock-on-objects-with-weak-identity.md)|Nepoužívejte zámky u objektů se slabou identitou|
|[CA2100](../code-quality/ca2100-review-sql-queries-for-security-vulnerabilities.md)|Zkontrolujte chyby zabezpečení u dotazů SQL|
|[CA2101](../code-quality/ca2101-specify-marshaling-for-p-invoke-string-arguments.md)|Určete zařazování pro argumenty řetězce volání nespravovaného kódu|
|[CA2108](../code-quality/ca2108-review-declarative-security-on-value-types.md)|Zkontrolujte deklarativní zabezpečení u typů hodnot|
|[CA2111](../code-quality/ca2111-pointers-should-not-be-visible.md)|Ukazatele by neměly být viditelné|
|[CA2112](../code-quality/ca2112-secured-types-should-not-expose-fields.md)|Zabezpečené typy by neměly vystavovat pole|
|[CA2114](../code-quality/ca2114-method-security-should-be-a-superset-of-type.md)|Zabezpečení metod by mělo být nadmnožinou typu|
|[CA2116](../code-quality/ca2116-aptca-methods-should-only-call-aptca-methods.md)|Metody APTCA by měly volat pouze metody APTCA|
|[CA2117](../code-quality/ca2117-aptca-types-should-only-extend-aptca-base-types.md)|Typy APTCA by měl rozšiřovat pouze základní typy APTCA|
|[CA2122](../code-quality/ca2122-do-not-indirectly-expose-methods-with-link-demands.md)|Nezveřejňujte nepřímo metody s požadavky propojení|
|[CA2123](../code-quality/ca2123-override-link-demands-should-be-identical-to-base.md)|Požadavky na propojení přepisů by měly být identické s bází|
|[CA2124](../code-quality/ca2124-wrap-vulnerable-finally-clauses-in-outer-try.md)|Zabalte ohroženou klauzuli finally do vnějšího bloku try|
|[CA2126](../code-quality/ca2126-type-link-demands-require-inheritance-demands.md)|Požadavky na propojení typů vyžadují požadavky na dědičnost|
|[CA2131](../code-quality/ca2131-security-critical-types-may-not-participate-in-type-equivalence.md)|Typy kritické pro zabezpečení se nesmí účastnit ekvivalence typů|
|[CA2132](../code-quality/ca2132-default-constructors-must-be-at-least-as-critical-as-base-type-default-constructors.md)|Výchozí konstruktory musí být alespoň tak kritické, jako výchozí konstruktory základního typu|
|[CA2133](../code-quality/ca2133-delegates-must-bind-to-methods-with-consistent-transparency.md)|Delegáti musí mít vazbu s metodami s konzistentní transparentností|
|[CA2134](../code-quality/ca2134-methods-must-keep-consistent-transparency-when-overriding-base-methods.md)|Metody musí při přepisování základních metod zachovávat konzistentní transparentnost|
|[CA2137](../code-quality/ca2137-transparent-methods-must-contain-only-verifiable-il.md)|Transparentní metody musí obsahovat pouze ověřitelné IL|
|[CA2138](../code-quality/ca2138-transparent-methods-must-not-call-methods-with-the-suppressunmanagedcodesecurity-attribute.md)|Transparentní metody nesmí volat metody s atributem SuppressUnmanagedCodeSecurity|
|[CA2140](../code-quality/ca2140-transparent-code-must-not-reference-security-critical-items.md)|Transparentní kód nesmí odkazovat na položky kritické pro zabezpečení|
|[CA2141](../code-quality/ca2141-transparent-methods-must-not-satisfy-linkdemands.md)|Transparentní metody nesmí splňovat LinkDemand.|
|[CA2146](../code-quality/ca2146-types-must-be-at-least-as-critical-as-their-base-types-and-interfaces.md)|Typy musí být alespoň tak kritické, jako jejich základní typy a rozhraní|
|[CA2147](../code-quality/ca2147-transparent-methods-may-not-use-security-asserts.md)|Transparentní metody nemusí používat kontrolní příkazy zabezpečení|
|[CA2149](../code-quality/ca2149-transparent-methods-must-not-call-into-native-code.md)|Transparentní metody nesmí provádět volání nativního kódu|
|[CA2200](../code-quality/ca2200-rethrow-to-preserve-stack-details.md)|Znovu vyvolejte pro zachování podrobností zásobníku|
|[CA2202](../code-quality/ca2202-do-not-dispose-objects-multiple-times.md)|Neuvolňujte objekty několikrát|
|[CA2207](../code-quality/ca2207-initialize-value-type-static-fields-inline.md)|Inicializujte statická pole s typem hodnoty vloženě|
|[CA2212](../code-quality/ca2212-do-not-mark-serviced-components-with-webmethod.md)|Neoznačujte obsluhované komponenty pomocí WebMethod|
|[CA2213](../code-quality/ca2213-disposable-fields-should-be-disposed.md)|Uvolnitelná pole by měla být uvolněna|
|[CA2214](../code-quality/ca2214-do-not-call-overridable-methods-in-constructors.md)|Nevolejte přepisovatelné metody v konstruktorech|
|[CA2216](../code-quality/ca2216-disposable-types-should-declare-finalizer.md)|Uvolnitelné typy by měly deklarovat finalizační metodu|
|[CA2220](../code-quality/ca2220-finalizers-should-call-base-class-finalizer.md)|Finalizační metody by měly volat finalizační metodu základní třídy|
|[CA2229](../code-quality/ca2229-implement-serialization-constructors.md)|Implementujte serializační konstruktory|
|[CA2231](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)|Přetižte operátor rovnosti při přetížení ValueType.Equals|
|[CA2232](../code-quality/ca2232-mark-windows-forms-entry-points-with-stathread.md)|Označte vstupní body modelu Windows Forms pomocí STAThread|
|[CA2235](../code-quality/ca2235-mark-all-non-serializable-fields.md)|Označte všechna neserializovatelná pole|
|[CA2236](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)|Volejte metody základní třídy u typů ISerializable|
|[CA2237](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)|Označte typy ISerializable pomocí SerializableAttribute|
|[CA2238](../code-quality/ca2238-implement-serialization-methods-correctly.md)|Implementujte správně metody serializace|
|[CA2240](../code-quality/ca2240-implement-iserializable-correctly.md)|Implementujte správně ISerializable|
|[CA2241](../code-quality/ca2241-provide-correct-arguments-to-formatting-methods.md)|Zadejte správné argumenty pro metody formátování|
|[CA2242](../code-quality/ca2242-test-for-nan-correctly.md)|Testujte správně NaN|
|[CA1000](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)|Nedeklarujte statické členy v obecných typech|
|[CA1002](../code-quality/ca1002-do-not-expose-generic-lists.md)|Nezveřejňujte obecné seznamy|
|[CA1003](../code-quality/ca1003-use-generic-event-handler-instances.md)|Použijte instance obecných obslužných rutin události|
|[CA1004](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)|Obecné metody by měly poskytnout parametr typu|
|[CA1005](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)|Vyhněte se nadbytečným parametrům u obecných typů|
|[CA1006](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)|Nevnořujte obecné typy do signatur členu|
|[CA1007](../code-quality/ca1007-use-generics-where-appropriate.md)|Použijte obecné typy, kde je to vhodné|
|[CA1008](../code-quality/ca1008-enums-should-have-zero-value.md)|Výčty by měly mít nulovou hodnotu|
|[CA1010](../code-quality/ca1010-collections-should-implement-generic-interface.md)|Kolekce musí implementovat obecné rozhraní|
|[CA1011](../code-quality/ca1011-consider-passing-base-types-as-parameters.md)|Zvažte předání základních typů jako parametrů|
|[CA1012](../code-quality/ca1012-abstract-types-should-not-have-constructors.md)|Abstraktní typy by neměly mít konstruktory|
|[CA1013](../code-quality/ca1013-overload-operator-equals-on-overloading-add-and-subtract.md)|Přetižte operátor rovnosti společně s přetížením operátorů sčítání a odečítání|
|[CA1014](../code-quality/ca1014-mark-assemblies-with-clscompliantattribute.md)|Označte sestavení pomocí CLSCompliantAttribute|
|[CA1017](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)|Označte sestavení pomocí ComVisibleAttribute|
|[CA1018](../code-quality/ca1018-mark-attributes-with-attributeusageattribute.md)|Označte atributy pomocí AttributeUsageAttribute|
|[CA1019](../code-quality/ca1019-define-accessors-for-attribute-arguments.md)|Definujte přístupové objekty pro argumenty atributů|
|[CA1023](../code-quality/ca1023-indexers-should-not-be-multidimensional.md)|Indexery by neměly být multidimenzionální|
|[CA1024](../code-quality/ca1024-use-properties-where-appropriate.md)|Použijte vlastnosti, kde je to vhodné|
|[CA1025](../code-quality/ca1025-replace-repetitive-arguments-with-params-array.md)|Nahraďte opakované argumenty polem parametrů|
|[CA1026](../code-quality/ca1026-default-parameters-should-not-be-used.md)|Neměly by být použity výchozí parametry|
|[CA1027](../code-quality/ca1027-mark-enums-with-flagsattribute.md)|Označte výčty pomocí FlagsAttribute|
|[CA1028](../code-quality/ca1028-enum-storage-should-be-int32.md)|Úložiště výčtu by mělo být Int32|
|[CA1030](../code-quality/ca1030-use-events-where-appropriate.md)|Použijte události, kde je to vhodné|
|[CA1031](../code-quality/ca1031-do-not-catch-general-exception-types.md)|Nezachycujte výjimky obecného typu|
|[CA1032](../code-quality/ca1032-implement-standard-exception-constructors.md)|Implementujte standardní konstruktory výjimky|
|[CA1034](../code-quality/ca1034-nested-types-should-not-be-visible.md)|Vnořené typy by neměly být viditelné|
|[CA1035](../code-quality/ca1035-icollection-implementations-have-strongly-typed-members.md)|Implementace ICollection mají členy silného typu|
|[CA1036](../code-quality/ca1036-override-methods-on-comparable-types.md)|Přepište metody u srovnatelných typů|
|[CA1038](../code-quality/ca1038-enumerators-should-be-strongly-typed.md)|Enumerátory by měly být silného typu|
|[CA1039](../code-quality/ca1039-lists-are-strongly-typed.md)|Seznamy jsou silného typu|
|[CA1041](../code-quality/ca1041-provide-obsoleteattribute-message.md)|Poskytněte zprávu ObsoleteAttribute|
|[CA1043](../code-quality/ca1043-use-integral-or-string-argument-for-indexers.md)|Použijte celočíselný nebo řetězcový argument pro indexery|
|[CA1044](../code-quality/ca1044-properties-should-not-be-write-only.md)|Vlastnosti by neměly být pouze pro zápis|
|[CA1046](../code-quality/ca1046-do-not-overload-operator-equals-on-reference-types.md)|Nepřetěžujte operátory rovnosti u odkazových typů|
|[CA1047](../code-quality/ca1047-do-not-declare-protected-members-in-sealed-types.md)|Nedeklarujte chráněné členy v zapečetěných typech|
|[CA1048](../code-quality/ca1048-do-not-declare-virtual-members-in-sealed-types.md)|Nedeklarujte virtuální členy v zapečetěných typech|
|[CA1050](../code-quality/ca1050-declare-types-in-namespaces.md)|Deklarujte typy v oborech názvů|
|[CA1051](../code-quality/ca1051-do-not-declare-visible-instance-fields.md)|Nedeklarujte viditelná pole instance|
|[CA1052](../code-quality/ca1052-static-holder-types-should-be-sealed.md)|Statické typy vlastníků by měly být zapečetěné|
|[CA1053](../code-quality/ca1053-static-holder-types-should-not-have-constructors.md)|Statické typy vlastníků by neměly mít konstruktory|
|[CA1054](../code-quality/ca1054-uri-parameters-should-not-be-strings.md)|Parametry identifikátoru URI by neměly být řetězce|
|[CA1055](../code-quality/ca1055-uri-return-values-should-not-be-strings.md)|Návratové hodnoty identifikátoru URI by neměly být řetězce|
|[CA1056](../code-quality/ca1056-uri-properties-should-not-be-strings.md)|Vlastnosti identifikátoru URI by neměly být řetězce|
|[CA1057](../code-quality/ca1057-string-uri-overloads-call-system-uri-overloads.md)|Přetížení řetězce identifikátoru URI volají přetížení System.Uri|
|[CA1058](../code-quality/ca1058-types-should-not-extend-certain-base-types.md)|Typy by neměly rozšiřovat určité základní typy|
|[CA1059](../code-quality/ca1059-members-should-not-expose-certain-concrete-types.md)|Členy by neměly zveřejňovat určité konkrétní typy|
|[CA1064](../code-quality/ca1064-exceptions-should-be-public.md)|Výjimky by měly být veřejné|
|[CA1500](../code-quality/ca1500-variable-names-should-not-match-field-names.md)|Názvy proměnných by neměly odpovídat názvům polí|
|[CA1502](../code-quality/ca1502-avoid-excessive-complexity.md)|Vyhněte se nadměrné složitosti|
|[CA1708](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)|Identifikátory by se měly lišit více než použitím malých a velkých písmen|
|[CA1716](../code-quality/ca1716-identifiers-should-not-match-keywords.md)|Identifikátory by se neměly shodovat s klíčovými slovy|
|[CA1801](../code-quality/ca1801-review-unused-parameters.md)|Zkontrolujte nepoužité parametry|
|[CA1804](../code-quality/ca1804-remove-unused-locals.md)|Odeberte nepoužívané lokální hodnoty|
|[CA1809](../code-quality/ca1809-avoid-excessive-locals.md)|Vyhněte se nadměrným lokálním hodnotám|
|[CA1810](../code-quality/ca1810-initialize-reference-type-static-fields-inline.md)|Inicializujte odkazový typ statického pole vloženě|
|[CA1811](../code-quality/ca1811-avoid-uncalled-private-code.md)|Vyhněte se nevolanému privátnímu kódu|
|[CA1812](../code-quality/ca1812-avoid-uninstantiated-internal-classes.md)|Vyhněte se nevytvořeným instancím interních tříd|
|[CA1813](../code-quality/ca1813-avoid-unsealed-attributes.md)|Vyhněte se nezapečetěným atributům|
|[CA1814](../code-quality/ca1814-prefer-jagged-arrays-over-multidimensional.md)|Upřednostněte vícenásobná pole před multidimenzionálními|
|[CA1815](../code-quality/ca1815-override-equals-and-operator-equals-on-value-types.md)|Přepište rovnosti a operátory rovnosti u typů hodnot|
|[CA1819](../code-quality/ca1819-properties-should-not-return-arrays.md)|Vlastnosti by neměly vracet pole|
|[CA1820](../code-quality/ca1820-test-for-empty-strings-using-string-length.md)|Testujte prázdné řetězce pomocí délky řetězce|
|[CA1822](../code-quality/ca1822-mark-members-as-static.md)|Označte členy jako statické|
|[CA1823](../code-quality/ca1823-avoid-unused-private-fields.md)|Vyhněte se nepoužitým privátním polím|
|[CA2201](../code-quality/ca2201-do-not-raise-reserved-exception-types.md)|Nevyvolávejte vyhrazené typy výjimek|
|[CA2205](../code-quality/ca2205-use-managed-equivalents-of-win32-api.md)|Použijte spravované ekvivalenty rozhraní Win32 API|
|[CA2208](../code-quality/ca2208-instantiate-argument-exceptions-correctly.md)|Vytvořte správně instance výjimky argumentu|
|[CA2211](../code-quality/ca2211-non-constant-fields-should-not-be-visible.md)|Nekonstantní pole by neměla být viditelná|
|[CA2217](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)|Neoznačujte výčty pomocí FlagsAttribute|
|[CA2219](../code-quality/ca2219-do-not-raise-exceptions-in-exception-clauses.md)|Nevyvolávejte výjimky v klauzulích výjimky|
|[CA2221](../code-quality/ca2221-finalizers-should-be-protected.md)|Finalizační metody by měly být chráněné|
|[CA2222](../code-quality/ca2222-do-not-decrease-inherited-member-visibility.md)|Nesnižujte viditelnost zděděného členu|
|[CA2223](../code-quality/ca2223-members-should-differ-by-more-than-return-type.md)|Členy by se měly lišit více než návratovým typem|
|[CA2224](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)|Přepište Equals při přetížení operátoru rovnosti|
|[CA2225](../code-quality/ca2225-operator-overloads-have-named-alternates.md)|Přetížení operátoru mají pojmenované alternativy|
|[CA2226](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)|Operátory by měly mít symetrická přetížení|
|[CA2227](../code-quality/ca2227-collection-properties-should-be-read-only.md)|Vlastnosti kolekce by měly být pouze pro čtení|
|[CA2230](../code-quality/ca2230-use-params-for-variable-arguments.md)|Použijte parametry pro proměnné argumenty|
|[CA2234](../code-quality/ca2234-pass-system-uri-objects-instead-of-strings.md)|Předejte objekty System.Uri namísto řetězců|
|[CA2239](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)|Zadejte metody deserializace pro nepovinná pole|
|[CA1020](../code-quality/ca1020-avoid-namespaces-with-few-types.md)|Vyhněte se oborům názvu s malým množstvím typů|
|[CA1021](../code-quality/ca1021-avoid-out-parameters.md)|Vyhněte se výstupním parametrům|
|[CA1040](../code-quality/ca1040-avoid-empty-interfaces.md)|Vyhněte se prázdným rozhraním|
|[CA1045](../code-quality/ca1045-do-not-pass-types-by-reference.md)|Nepředávejte typy odkazem|
|[CA1062](../code-quality/ca1062-validate-arguments-of-public-methods.md)|Ověřte argumenty veřejných metod|
|[CA1501](../code-quality/ca1501-avoid-excessive-inheritance.md)|Vyhněte se nadměrné dědičnosti|
|[CA1504](../code-quality/ca1504-review-misleading-field-names.md)|Zkontrolujte zavádějící názvy polí|
|[CA1505](../code-quality/ca1505-avoid-unmaintainable-code.md)|Vyhněte se neudržovatelnému kódu|
|[CA1506](../code-quality/ca1506-avoid-excessive-class-coupling.md)|Vyhněte se nadměrnému párování tříd|
|[CA1700](../code-quality/ca1700-do-not-name-enum-values-reserved.md)|Nepojmenovávejte výčty hodnot 'Reserved'|
|[CA1701](../code-quality/ca1701-resource-string-compound-words-should-be-cased-correctly.md)|Malá a velká písmena složených slov řetězců prostředků by měla být použita správně|
|[CA1702](../code-quality/ca1702-compound-words-should-be-cased-correctly.md)|Malá a velká písmena složených slov by měla být použita správně|
|[CA1703](../code-quality/ca1703-resource-strings-should-be-spelled-correctly.md)|Řetězce prostředků by měly být zadány správně|
|[CA1704](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)|Identifikátory by měly být zadány správně|
|[CA1707](../code-quality/ca1707-identifiers-should-not-contain-underscores.md)|Identifikátory by neměly obsahovat podtržítka|
|[CA1709](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)|Malá a velká písmena identifikátorů by měla být použita správně|
|[CA1710](../code-quality/ca1710-identifiers-should-have-correct-suffix.md)|Identifikátory by měly mít správnou příponu|
|[CA1711](../code-quality/ca1711-identifiers-should-not-have-incorrect-suffix.md)|Identifikátory by neměly mít nesprávnou příponu|
|[CA1712](../code-quality/ca1712-do-not-prefix-enum-values-with-type-name.md)|Nezačínejte hodnoty výčtu názvem typu|
|[CA1713](../code-quality/ca1713-events-should-not-have-before-or-after-prefix.md)|Události by neměly mít předponu před nebo po|
|[CA1714](../code-quality/ca1714-flags-enums-should-have-plural-names.md)|Výčty příznaků by neměly mít názvy v množném čísle|
|[CA1715](../code-quality/ca1715-identifiers-should-have-correct-prefix.md)|Identifikátory by měly mít správnou předponu|
|[CA1717](../code-quality/ca1717-only-flagsattribute-enums-should-have-plural-names.md)|Pouze výčty FlagsAttribute by měly mít názvy v množném čísle|
|[CA1719](../code-quality/ca1719-parameter-names-should-not-match-member-names.md)|Názvy parametrů by se neměly shodovat s názvy členů|
|[CA1720](../code-quality/ca1720-identifiers-should-not-contain-type-names.md)|Identifikátory by neměly obsahovat názvy typů|
|[CA1721](../code-quality/ca1721-property-names-should-not-match-get-methods.md)|Názvy vlastností by se neměly shodovat s metodami Get|
|[CA1722](../code-quality/ca1722-identifiers-should-not-have-incorrect-prefix.md)|Identifikátory by neměly mít nesprávnou předponu|
|[CA1724](../code-quality/ca1724-type-names-should-not-match-namespaces.md)|Názvy typů by se neměly shodovat s obory názvů|
|[CA1725](../code-quality/ca1725-parameter-names-should-match-base-declaration.md)|Názvy parametrů by měly odpovídat základní deklaraci|
|[CA1726](../code-quality/ca1726-use-preferred-terms.md)|Použijte upřednostňované výrazy|
|[CA2204](../code-quality/ca2204-literals-should-be-spelled-correctly.md)|Literály by měly být zadány správně|