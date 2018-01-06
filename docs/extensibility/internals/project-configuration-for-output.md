---
title: "Konfigurace pro výstup projektu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: project configurations, output
ms.assetid: a4517f73-45af-4745-9d7f-9fddf887b636
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 4f3927ac9aa9e85be026d2b9a2af1c0c4d956c9f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="project-configuration-for-output"></a>Konfigurace projektu pro výstup
Všechny konfigurace dokáže zajistit podporu sadu sestavení procesy, které vytvoří výstupní položek, jako jsou soubory spustitelný soubor nebo prostředků. Tyto položky výstupní jsou soukromá pro uživatele a mohou být umístěny ve skupinách, které odkazují souvisejících typů výstupu, jako je například spustitelné soubory (.exe, .dll, .lib) a zdrojových souborů (.idl, souborů .h).  
  
 Výstupní položky může být k dispozici prostřednictvím <xref:Microsoft.VisualStudio.Shell.Interop.IVsOutput2> metody a výčtové s <xref:Microsoft.VisualStudio.Shell.Interop.IVsEnumOutputs> metody. Pokud chcete seskupení položek výstup by měl taky implementovat projektu <xref:Microsoft.VisualStudio.Shell.Interop.IVsOutputGroup> rozhraní.  
  
 Konstruktu vyvinuté implementace `IVsOutputGroup` umožňuje projekty tak, aby skupina výstupy podle využití. Knihovny DLL pro instanci, mohou být seskupeny s jeho databázi programu (PDB).  
  
> [!NOTE]
>  Obsahuje informace o ladění do souboru PDB a je vytvořen, pokud je zadána možnost "Generovat ladicí informace při sestavování .dll nebo .exe. Na soubor .pdb je obvykle vygenerované pouze konfiguraci ladění projektu.  
  
 Projekt musí vrátit stejný počet skupin pro každé konfiguraci, kterou podporuje, i když počet výstupů obsažena ve skupině se může lišit od konfigurace. Například projektu Matt knihoven DLL může zahrnovat mattd.dll a mattd.pdb v konfiguraci ladění, ale pouze zahrnout matt.dll prodejní konfiguraci.  
  
 Skupiny také mít stejný identifikátor informace, například název v kanonickém tvaru, zobrazovaný název a informace skupiny z konfigurace v rámci projektu. Tato konzistence umožňuje nasazení a balení nadále fungovat i v případě, že změna konfigurace.  
  
 Skupiny mohou mít také klíče výstupu, který umožňuje balení zástupce tak, aby odkazoval na něco smysluplného. Všechny skupiny může být prázdná v dané konfiguraci, takže žádné předpoklady třeba o velikosti skupiny. Velikost (počet výstupů) v jakékoli konfiguraci každé skupiny se může lišit od velikosti jiné skupiny ve stejné konfiguraci. Může být také liší od velikost stejné skupiny v jinou konfiguraci.  
  
 ![Obrázek skupin výstup](../../extensibility/internals/media/vsoutputgroups.gif "vsOutputGroups")  
Skupiny výstupu  
  
 Primárním použitím <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg> rozhraní je poskytnout přístup k vytvoření, nasazení a ladění objekty pro správu a povolit projekty volného výstupy skupiny. Další informace o použití tohoto rozhraní najdete v tématu [objekt konfigurace projektu](../../extensibility/internals/project-configuration-object.md).  
  
 Na předchozím obrázku, vytvořené skupiny má klíč výstup mezi konfigurací (bD.exe nebo b.exe), tak uživatel můžete vytvořit zástupce předdefinované a vědět, že zástupce bude fungovat bez ohledu na nastavení nasazení. Skupiny zdroj nemá klíč výstup, takže uživatele nelze vytvořit zástupce do ní. Pokud ladění skupiny vytvořené má klíče výstup, ale prodejní skupiny vytvořené nemá, který by nesprávné implementace. Přistoupit, pak Pokud žádnou konfiguraci má skupinu, která obsahuje žádné výstupy, a v důsledku toho se soubory klíčů nemají žádný soubor klíče a pak ostatní konfigurace s této skupiny, které obsahují výstupy. Editory instalační program předpokládá, že kanonické názvy a zobrazované názvy skupin a navíc existenci soubor klíče, neměňte na základě v konfiguracích.  
  
 Všimněte si, že pokud má projektu `IVsOutputGroup` že nechce balíček nebo nasazení, bude stačit není uvést tento výstup do skupiny. Výstup mohou být stále normálně uvedené implementací <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg.EnumOutputs%2A> metoda, která vrátí všechny výstupy konfigurace bez ohledu na to seskupení.  
  
 Další informace najdete v tématu implementace `IVsOutputGroup` v ukázce vlastní projektu na [sady MPF projektů](http://mpfproj12.codeplex.com).  
  
## <a name="see-also"></a>Viz také  
 [Správa možnosti konfigurace](../../extensibility/internals/managing-configuration-options.md)   
 [Konfigurace projektu pro vytváření](../../extensibility/internals/project-configuration-for-building.md)   
 [Objekt konfigurace projektu](../../extensibility/internals/project-configuration-object.md)   
 [Konfigurace řešení](../../extensibility/internals/solution-configuration.md)