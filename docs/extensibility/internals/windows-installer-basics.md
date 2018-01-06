---
title: "Základy Instalační služby systému Windows | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Installer, VSPackages
- VSPackages, Windows Installer basics
ms.assetid: 497e479b-add8-4644-870a-917f15306b97
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 1a9f895db0d202dd573e7c665b1185f6e3f4b751
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="windows-installer-basics"></a>Základy Instalační služby systému Windows
Instalační služba systému Windows instaluje a odinstaluje aplikace nebo softwarové produkty na počítači uživatele, provádění těchto úkolů v jednotkách nazývané jako komponenty Instalační služby systému Windows (někdy nazývané WICs nebo jenom komponenty). Identifikátor GUID identifikuje každého WIC, což je základní jednotkou instalace a u instalace pomocí Instalační služby systému Windows při počítání referencí.  
  
 Úplnou dokumentaci Instalační služby systému Windows, naleznete v tématu Platform SDK [Instalační služby systému Windows](http://msdn.microsoft.com/library/aa372866.aspx).  
  
## <a name="authoring-a-vspackage"></a>Vytváření VSPackage  
 Instalační služba systému Windows používá instalační balíčky, které obsahují informace, které instalační služba systému Windows je potřeba instalovat, odinstalovat nebo oprava produktu a spustit instalační program uživatelské rozhraní (UI). Každý instalační balíček obsahuje soubor MSI, která obsahuje instalační databázi, souhrnné informace a datové proudy pro různé součásti instalace. Pokud chcete použít instalační program, musíte napsat instalace. Vzhledem k tomu, že instalační program organizuje instalace kolem koncept součásti a ukládá informace o instalaci v relační databázi, proces vytváření instalační balíček široce zahrnuje následující kroky:  
  
1.  Plánování vašeho nastavení vytváření pro podporu správy verzí a strategie vedle sebe.  
  
2.  Určete funkce, která předkládá uživatelům.  
  
3.  Uspořádání VSPackage a závislosti do součásti.  
  
4.  Naplnění databáze instalace informace.  
  
5.  Ověření instalace balíčku.  
  
 Tato dokumentace se týká především první a třetí kroky procesu. Při provádění těchto kroků můžete uspořádat vaše VSPackage funkce do WICs tak můžete rámce vaší verze a údržba strategie pro účet pro další verze [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Zbývající tři kroky jsou podrobně popsány v dokumentaci Instalační služby systému Windows v sadě SDK pro platformu.  
  
## <a name="key-terms"></a>Klíčových pojmů  
 Následují definice klíčových pojmů související technologie Instalační služby systému Windows.  
  
 Prostředek  
 Soubory, zástupce a klíče registru nebo a tak dále, může se nainstalovat do počítače. Tyto prostředky jsou logicky seskupeny do součásti Instalační služby systému Windows.  
  
 Součást Instalační služby systému Windows (WIC)  
 Základní jednotka instalace představující logické seskupení souvisejících prostředků, které se instaluje a odinstaluje jako jednotku. Instalační služba systému Windows součásti jsou označeny součást jedinečné ID nebo identifikátor GUID. Navíc Instalační služby systému Windows udržuje jeho na úrovni WIC při počítání referencí. Maximální verze flexibilitu zahrnují více než jeden primární prostředek, například knihovny DLL, v dané WIC. Všimněte si, že po identifikaci a naplnit WIC, zadejte pro něj identifikátor GUID a nasadíte ji, nelze změnit jeho složení. Další informace najdete v tématu [uspořádání aplikace do komponenty](http://msdn.microsoft.com/library/aa370561.aspx).  
  
 Balíček (Redist balíček)  
 Jednotka nasazení, který se skládá z soubor MSI a externí zdrojové soubory, ke kterým může bod tohoto souboru. Balíček obsahuje všechny informace, které instalační služba systému Windows je potřeba ke spuštění uživatelského rozhraní a instalace nebo odinstalace aplikace.  
  
 Soubor MSI  
 Soubor strukturovaná COM úložiště obsahující pokyny a data požadovaná k instalaci aplikace. Každý balíček obsahuje alespoň jeden soubor .msi. Soubor MSI obsahuje instalační databáze, datový proud s souhrnné informace a může být jeden nebo více transformací a interní zdrojové soubory. Soubory k instalaci můžete buď být komprimované do soubor CAB a uložená v datovém proudu v souboru .msi nebo uložené, komprimované nebo nekomprimovaným mimo soubor .msi na zdrojovém médiu. Další informace najdete v tématu [přípony souborů Instalační služby systému Windows](http://msdn.microsoft.com/library/aa372842\(VS.85\).aspx).  
  
## <a name="windows-installer-rules-enforcement"></a>Vynucení pravidel Instalační služby systému Windows  
 Dvě sady pravidel určit nasazení prostředků prostřednictvím součástí vašeho nastavení. Jedna sada pravidel se spravuje pomocí Instalační služby systému Windows, samostatně, zatímco by měl vynutit druhé sadě jako autor instalace.  
  
> [!NOTE]
>  Pouze v případě, že spustíte ověření vašeho souboru .msi, dojde k vynucení pravidel Instalační služby systému Windows. Nicméně jsou cautioned pro tato pravidla považovat za osvědčené postupy. Další informace najdete v tématu [ověřování instalační databázi](http://msdn.microsoft.com/library/aa372477\(VS.85\).aspx) a [ověřování balíčku](http://msdn.microsoft.com/library/aa370569\(VS.85\).aspx).  
  
#### <a name="installer-enforced-rules"></a>Vynucené instalační program pravidla  
  
-   Všechny soubory v dané součásti musí být nainstalována na stejném adresáři. Naopak soubory nainstalované do samostatné složky musí patřit do samostatné součásti.  
  
-   Může existovat jenom jednu cestu ke klíči za součást. Cesta klíče je jednoduše souborů nebo registru klíč, který představuje celou součást.  
  
#### <a name="component-provider-responsibilities"></a>Součást zprostředkovatele odpovědnosti  
  
-   Všechny dva prostředky, které může dodávat samostatně v budoucích verzích by měla existovat v samostatné součásti. Prostředky by měly být seskupené do stejné komponenty jenom v případě, že jste si jisti, že tyto prostředky se nikdy dodávat samostatně. Ve skutečnosti se doporučuje, všechny primární prostředky (například DLL) vždy existují v samostatných WICs. Další informace najdete v tématu [definování instalační program součásti](http://msdn.microsoft.com/library/aa368269\(VS.85\).aspx).  
  
-   Žádný verzí prostředek by měl někdy dodat ve více než jeden WIC.  
  
## <a name="see-also"></a>Viz také  
 [Co se stane, když součást pravidla jsou přerušená?](http://msdn.microsoft.com/library/aa372795\(VS.85\).aspx)