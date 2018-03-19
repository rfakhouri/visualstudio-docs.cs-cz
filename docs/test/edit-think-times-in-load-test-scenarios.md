---
title: "Dob uvažování pro zatížení testování v sadě Visual Studio | Microsoft Docs"
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- load tests, think times
- load tests, adding delays
- load tests, changing think times
ms.assetid: 8e03bee5-ab7b-4b40-9497-9dbe91ccb90e
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: cccf2961ceb5abecb33396433e344015143503bf
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2018
---
# <a name="edit-think-times-to-simulate-website-human-interaction-delays-in-load-tests-scenarios"></a>Úpravy dob uvažování pro simulaci prodlev při interakci s lidským webové stránky ve scénářích zátěžových testů

Dob uvažování se používají k simulaci lidského chování, jež způsobuje lidí, kteří budou čekat mezi interakce s webovou stránku. Dob uvažování dojít mezi požadavků v testu výkonnosti webu a mezi iterací testů ve scénáři zátěžového testu. Pomocí časů přemýšlení v zátěžovém testu může být užitečné při vytváření přesnější simulace zatížení. Jestli testy Považujte dobu používat nebo ignorovat v zatížení, můžete změnit. Můžete změnit, zda Považujte, kolikrát se používají v zatížení testy v editoru testu zatížení.

 *Vezměte v úvahu profil* je nastavení, které se vztahují na scénář v zátěžovém testu. Toto nastavení určuje, že zda Považujte časy jsou uloženy v jednotlivé testy výkonnosti webu se používá během zátěžového testu. Pokud chcete použít v některé testy výkonnosti webu časy přemýšlení, ale v jiných případech nesmí umístěte je v různých scénářích. Další informace o scénářích najdete v tématu [úpravy scénářů zátěžových testů](../test/edit-load-test-scenarios.md).

 Na začátku nastavíte časů přemýšlení při použití v zátěžových testech vytvořte zátěžový test pomocí nového načíst testování průvodce. Další informace najdete v tématu [úpravy scénářů zátěžových testů](../test/edit-load-test-scenarios.md).

 Vezměte v úvahu profil možnosti jsou popsané v následujícím seznamu:

**Off**

Dob uvažování se ignorují. Toto nastavení použijte, pokud chcete generovat maximální zátěž výraznou vystavila zátěži váš webový server. Nepoužívejte ho, když se pokoušíte vytvořit realističtější interakce uživatele s webového serveru.

**On**

Dob uvažování používají přesně tak, jak nebyly zaznamenány v testu výkonnosti webu. Simuluje spouštění testů výkonnosti webu přesně tak, jak zaznamenávají více uživatelů. Vzhledem k tomu, že simuluje zátěžový test víc uživatelů, používající stejný vezměte v úvahu, že čas vytvořit vzor nepřirozené zatížení synchronizovaných virtuálních uživatelů.

**Normální rozdělení**

Dob uvažování se používá, ale nejrůznější na normální křivky. Poskytuje realističtější simulace virtuálních uživatelů pomocí mírně různých Představte si, že doba mezi požadavky.

> [!NOTE]
> Úplný seznam vlastnosti scénáře zátěžového testu a jejich popisy najdete v tématu [načíst vlastnosti scénář otestovat](../test/load-test-scenario-properties.md).

## <a name="changing-the-think-profile"></a>Změně Představte si, že profil

### <a name="to-change-a-think-profile-in-a-load-test-scenario"></a>Chcete-li změnit profil Představte si, že ve scénáři zátěžového testu

1.  Z výkonu webu a zatížení testování projektu, otevřete zátěžový test.

2.  V **editoru zátěžových testů**, vyberte uzel scénář, ve které chcete změnit **vezměte v úvahu profil**. **Vezměte v úvahu profil** se zobrazí v okně Vlastnosti. Stisknutím klávesy F4 zobrazení okna Vlastnosti.

3.  Změna **vezměte v úvahu profil** vlastnost v okně Vlastnosti.

4.  Po dokončení změn vlastností zvolte **Uložit** na **souboru** nabídky. Když pak spustíte zátěžového testu s uvažování nový profil.

## <a name="see-also"></a>Viz také

- [Úpravy scénářů zátěžových testů](../test/edit-load-test-scenarios.md)