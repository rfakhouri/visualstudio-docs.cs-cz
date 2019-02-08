---
title: Syntaxe cesty domény
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, domain path
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 47c2adc2894cc67b337243c30f4a62bc3642ff39
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55955229"
---
# <a name="domain-path-syntax"></a>Syntaxe cesty domény
Definice DSL pomocí XPath syntaxe vyhledejte konkrétní prvky v modelu.

 Obvykle není potřeba pracovat přímo s následující syntaxí. Kde se zobrazí v okně Vlastnosti, nebo podrobnosti DSL můžete klepnutím na šipku dolů a v editoru cestu. Cesta se však zobrazí v tomto formuláři v poli po použití editoru.

 Doménová cesta má následující podobu:

 *RelationshipName.PropertyName/!Role*

 ![Referenční vztah CommentReferencesSubjects – odkazová](../modeling/media/dsl_reference.png)

 Syntaxe prochází stromu modelu. Například doménového vztahu **CommentReferencesSubjects – odkazová** na výše uvedeném obrázku má **Predmety** role. Segment cesty **/! Subjectt** Určuje, že cesta skončí u elementů přistupovat prostřednictvím **Predmety** role.

 Spustí se každý segment s názvem doménového vztahu. Pokud procházení je z elementu relace, segment cesty se zobrazí jako *Relationship.PropertyName*. Pokud ke směrování je z odkazu na prvek, segment cesty se zobrazí jako *vztah /! RoleName*.

 Lomítka samostatné syntaxe cesty. Každý segment cesty je směrování z elementu propojení (instance relace) nebo z odkazu na element. Segmenty cesty často vyskytovat v párech. Jeden segment cesty představuje hop z elementu propojení a další segment představuje hop z odkazu na prvek na druhém konci. (Odkaz může také být zdroj nebo cíl v relaci sama).

 Název, který používáte pro prvek odkazu směrování je hodnota této role `Property Name`. Název, který používáte pro prvek odkazu směrování je cílový název role.

## <a name="see-also"></a>Viz také

- [Porozumění modelům, třídám a vztahům](../modeling/understanding-models-classes-and-relationships.md)