---
title: Na kartě systém. Výběr položek sady nástrojů – dialogové okno | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- VS.CHOOSEITEMS.SYSTEM.ACTIVITIES_COMPONENTS
- VS.CHOOSEITEMS.SYSTEM.ACTIVITIES COMPONENTS
ms.assetid: cef390cd-eeda-42e6-9d2e-18c8325a4f06
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2da5aafcc684c9af71aebc094d817c64f579d0ea
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="systemactivities-tab-choose-toolbox-items-dialog-box"></a>Na kartě systém. Výběr položek sady nástrojů – dialogové okno
Na této kartě z **výběr položek sady nástrojů** dialogové okno zobrazí seznam [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] aktivit, šablony a dostupné položky. Chcete-li zobrazit tento seznam, vyberte **výběr položek sady nástrojů** z **nástroje** nabídky nebo kliknutím pravým tlačítkem **sada nástrojů** a výběrem **zvolit položky**zobrazíte **výběr položek sady nástrojů** dialogové okno a potom vyberte jeho **systém.** kartě. Předinstalované seznam obsahuje aktivity pracovního postupu z systém, System.ServiceModel.Activities a System.Activities.Core.Presentation sestavení; ale pouze poskytované systémem vidět a aktivity, které jsou přidány prostřednictvím ostatních sestavení se zobrazí v **sada nástrojů** jsou ve výchozím nastavení zaškrtnuto. Nedávno přidané aktivity jsou automaticky zkontrolovány a zobrazují v **sada nástrojů** když kliknete na tlačítko **OK** v dialogovém okně. Tyto položky nezobrazí, v **sada nástrojů** pod novou kategorii, která odpovídá do oboru názvů, které se nachází aktivity či položky nebo šablonu.

> [!WARNING]
> Pokud se pokusíte přidat sestavení, který neobsahuje žádné aktivity pracovního postupu, se zobrazí dialogové okno chyby, které vysvětluje, zda je sestavení neobsahuje žádné aktivity.

 Toto dialogové okno je nezávislá na projekt a proto **systém.** kartě nadále zobrazí v samostatné XAML nebo typu projektu mimo pracovní postup.

 Filtrování se provádí na každé kartě. To znamená, že není možné přidat aktivity pracovních postupů prostřednictvím **součásti rozhraní .NET** kartě. Musí být přidány prostřednictvím **systém.** kartě sám sebe.

 Můžete zrušit zaškrtnutí všech položek, které nechcete zobrazit v **sada nástrojů** z toto dialogové okno karty, nebo alternativně, můžete to provést pomocí **odstranit** možnost místní nabídky v **sada nástrojů** a zrušte odkazování na sestavení neodebere položku z **sada nástrojů**.

 Vytváření instancí aktivity, pomocí přetahování a vkládání v designeru přidá sestavení, které obsahuje položky do seznamu odkazovaná sestavení automaticky. Také pokud aktivity odkazuje na sestavení C, se nepřidá C do seznamu odkazované sestavení. Sestavení C musí být v mezipaměti GAC nebo stejného adresáře jako aktivita B. V případě samostatné sestavení musí být v mezipaměti GAC nebo cesty testu VS. Pak můžete můžete přetáhnout aktivity na plochu návrháře pracovního postupu.

 **Sada nástrojů** nastavení se ukládají ve výchozím nastavení jako uživatelské možnosti, proto další čas, při otevření **sada nástrojů**, se zobrazí seznam vlastní aktivity pracovního postupu. Jeden vedlejším účinkem této je, že pokud jste přidali své konkrétní doménu položky k **sada nástrojů** prostřednictvím **výběr položek sady nástrojů** dialogové okno, můžete nadále tyto položky zobrazit, když pracujete Pracovní postup také konzolové aplikace. Pokud nechcete, aby byla zobrazena, je pomocí místní nabídky odstranit nebo zrušte zaškrtnutí políčka je prostřednictvím **výběr položek sady nástrojů** dialogového okna jak už jsme zmínili dřív.

 Sloupce v tomto seznamu obsahují následující informace:

 Zobrazí název názvy aktivit pracovního postupu, které jsou aktuálně registrované na místním počítači.

 Namespace zobrazí hierarchii knihovna tříd rozhraní .NET Framework obor názvů, který definuje strukturu aktivity.

 Název sestavení zobrazí název a verze sestavení rozhraní .NET Framework, který obsahuje aktivitu.

 Directory zobrazí umístění sestavení rozhraní .NET Framework, který obsahuje aktivity pracovního postupu. Je výchozím umístěním pro všechny sestavení do globální mezipaměti sestavení.

 Chcete-li seřadit uvedených součástí, vyberte záhlaví libovolného sloupce.