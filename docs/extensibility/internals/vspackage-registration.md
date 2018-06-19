---
title: Registrace VSPackage | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- registration, VSPackages
- VSPackages, registering
ms.assetid: ecd20da8-b04b-4141-a8f4-a2ef91dd597a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 348010982b015eaf19ba4de559eca66bb24930a3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31148883"
---
# <a name="vspackage-registration"></a>VSPackage registrace
Musíte poradit VSPackages [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] že jsou nainstalovány a že má být načten. Tento proces se provádí zápis informace v registru. To je typické úlohy instalačního programu.  
  
> [!NOTE]
>  Přijatý postupem je během vývoje VSPackage používat vlastní registraci. Ale [!INCLUDE[vsipprvsip](../../extensibility/includes/vsipprvsip_md.md)] partnery nemůžete dodat jejich produkty, které používají vlastní registraci jako součást instalace.  
  
 Položky registru do balíčku Instalační služby systému Windows jsou obecně vytvářeny v tabulce registru. Můžete také registrovat přípony souborů v tabulce registru. Instalační služba systému Windows, ale poskytuje integrovanou podporu prostřednictvím programový identifikátor (ProgId), třídu, rozšíření a operaci tabulky. Další informace najdete v tématu [databázových tabulek](http://msdn.microsoft.com/library/aa368259\(VS.85\).aspx).  
  
 Ujistěte se, že vaše položky registru jsou spojeny s komponentu, který je vhodný pro strategie vybrané vedle sebe. Položky registru pro sdílený soubor například by měly být přidruženy s použitím komponenty tento soubor Instalační služby systému Windows. Položky registru pro specifické pro verzi souboru, by měly být přidruženy s použitím komponenty tento soubor. Jinak, instalace nebo odinstalace vaší VSPackage pro jednu verzi [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] by mohlo způsobit narušení vaší VSPackage v dalších verzích. Další informace najdete v tématu [podpora více verzí aplikace Visual Studio](../../extensibility/supporting-multiple-versions-of-visual-studio.md)  
  
> [!NOTE]
>  Nejjednodušší způsob, jak spravovat registraci se má používat stejná data ve stejné soubory, které pro vývojáře registrace a instalace registrace. Například některé nástroje pro vývoj instalační program může využít soubor ve formátu .reg v čase vytvoření buildu. Pokud vývojářům udržovat .reg soubory pro své vlastní každodenní vývoj a ladění, tyto stejné soubory můžou být součástí instalační program automaticky. Pokud nemůžete sdílet automaticky registrační data, je nutné zajistit, že je aktuální kopii instalačního programu registrační data.  
  
## <a name="registering-unmanaged-vspackages"></a>Registrace nespravované VSPackages  
 Nespravované VSPackages (včetně těch generované šabloně balíček Visual Studio) ATL stylu .rgs soubory použít k uložení informace o registraci. Formát souboru .rgs je specifická pro knihovny ATL a nejde je obecně využívat jako-je nástroj pro tvorbu instalací. Informace o registraci pro instalační program VSPackage musí být udržovány odděleně. Například vývojáři mohou synchronizaci souborů ve formátu .reg s .rgs změny souboru. Soubory .reg můžete sloučit s RegEdit pro vývojové práci nebo spotřebovávají instalační program.  
  
## <a name="registering-managed-vspackages"></a>Registrace spravované VSPackages  
 Nástroj RegPkg přečte atributy registrace ze spravovaných VSPackage a může buď zapsat informace přímo do registru nebo soubory ve formátu .reg zápisu, které mohou být spotřebovávána instalační program.  
  
> [!NOTE]
>  Nástroj RegPkg není redistributable a nemůže být použitý k registraci VSPackage na uživatele systému.  
  
## <a name="why-vspackages-should-not-self-register-at-install-time"></a>Proč VSPackages měli není samoobslužné zaregistrovat v době instalace  
 Vaše instalační programy VSPackage neměli spoléhat na automatickou registraci. Na první pohled zachování hodnoty registru VSPackage pouze v VSPackage samotné zdá se, že jako vhodné. Oznámeno, že vývojáři pro své běžné pracovní potřebovat dostupné hodnoty registru a testování, má smysl, aby se zabránilo zachování samostatnou kopii dat registru v instalačním programu. Instalační program může se spoléhat na samotný VSPackage zápis hodnoty registru.  
  
 Při dobré teoreticky automatickou registraci má několik nedostatky, které není vhodný pro instalaci VSPackage:  
  
-   Správně podpora instalace, odinstalace, vrácení instalace zpět a odinstalace vrácení vyžaduje, abyste vytvořit čtyři vlastní akce pro každý spravovaný VSPackage, který samoobslužné zaregistruje voláním RegPkg.  
  
-   Váš přístup k zajištění podpory vedle sebe může vyžadovat, že vytváříte čtyři vlastní akce, které vyvolat příkaz RegSvr32 nebo RegPkg pro každou podporovanou verzi [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
-   Instalace s vlastním registrovaných modulů nelze bezpečně odvolat, protože neexistuje žádný způsob sdělit, pokud automaticky registrována klíče se používají jiné funkce nebo aplikace.  
  
-   Automaticky registrována knihovny DLL někdy propojit pomocné knihovny DLL, které neexistují nebo jsou nesprávné verze. Instalační služba systému Windows, můžete zaregistrovat knihovny DLL pomocí tabulky registru žádná závislost na aktuální stav systému.  
  
-   Vlastní registraci kódu můžete odepřen přístup k síťovým prostředkům, například knihovny typů, pokud je součást současně zadány jako spustit ze zdroje a je uveden v tabulce SelfReg. To může způsobit instalace součásti selhání během instalace pro správu.  
  
## <a name="see-also"></a>Viz také  
 [Instalační služba systému Windows](http://msdn.microsoft.com/library/cc185688\(VS.85\).aspx)   
 [Registrace spravované balíčku](http://msdn.microsoft.com/en-us/f69e0ea3-6a92-4639-8ca9-4c9c210e58a1)