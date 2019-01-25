---
title: Práce se shadery | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: 6b2ea1ed-b995-4e75-af19-c68fd37a3bc5
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 3e0f962440d722a881d7a8de4ed2e7c9a9c7755f
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54795907"
---
# <a name="working-with-shaders"></a>Práce se shadery
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Můžete použít grafické návrháře shaderu v [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] návrhu vlastní shaderu účinky. Můžete použít tyto shaderů založené na rozhraní DirectX hře nebo aplikaci.  
  
## <a name="shaders"></a>Shadery  
 A *shaderu* je počítačový program, který provádí výpočty grafiky – například transformace vrchol nebo pixel barevné – obvykle běží na grafický procesor (GPU) namísto procesoru. Protože většina fáze zřetězení grafiky tradiční, funkce teď provádí shaderu programy, je můžete použít k vytvoření kanálu, která jsou specifická podle potřeb vaší aplikace.  
  
 Nejběžnější typy shaderů se *vertex shader*, který provádění výpočtů na vrcholu a nahraďte transformace – funkce a obvody osvětlení v Neprogramovatelná grafický hardware, a *pixelů shadery*, které provádějí výpočty jednotlivých pixelů, které určit barva pixel a nahraďte barva function kombinační obvod v Neprogramovatelná grafický hardware. Moderní grafický hardware provedl i další typy shaderů je to možné –*shadery trupu*, *domény shadery*, a *geometry shader* pro grafické výpočty a *výpočetní shadery* pro výpočty bez grafiky. Žádná z těchto fází jsou dostupné v Neprogramovatelná grafický hardware. Shadery byly původně vytvořeny pomocí sestavení jazyk, který poskytuje paralelizovaného pro data (SIMD) a pokyny zaměřené na grafiky (součin). Nyní shadery se obvykle vytvářejí pomocí vysoké úrovně, jako v jazyce C jazyky, jako je HLSL (vysokou úroveň Shader Language).  
  
 Návrháře shaderu slouží k vytvoření pixel shaderů interaktivně namísto z zadáním a kompilaci kódu. V Návrháři shaderu shaderu určen počet uzlů, které představují data a operace a připojení mezi uzly, které představují toku datových hodnot a mezilehlých výsledků prostřednictvím shaderu. Pomocí tohoto přístupu a v reálném čase ve verzi preview v Návrháři shaderu, můžete snadněji vizualizovat spouštění shaderu a "objevit" zajímavé variace shaderu prostřednictvím služby experimentování ve službě.  
  
## <a name="dgsl-documents"></a>Dokumenty DGSL  
 Návrháře shaderu uloží shadery ve formátu orientovaného grafu Shader Language (DGSL), který je ve formátu XML, který je založen na orientovaného grafu jazyka přímého značení (DGML). Shader DGSL můžete použít přímo pro 3D modely v editoru modelů. Ale ve vaší aplikaci mohli používat DGSL shader, je nutné ho exportovat do formátu srozumitelného DirectX – například HLSL.  
  
 Protože DGSL je kompatibilní s DGML, můžete použít nástroje, které jsou určeny k analýze dokumentech DGML k analýze vaší DGSL shader. Informace o DGML, naleznete v tématu [Principy orientovaného grafu jazyka přímého značení (DGML)](http://msdn.microsoft.com/library/ee842619.aspx).  
  
## <a name="related-topics"></a>Související témata  
  
|Název|Popis|  
|-----------|-----------------|  
|[Návrhář shaderů](../designers/shader-designer.md)|Popisuje způsob použití [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] návrháře shaderu pro práci se shadery.|  
|[Uzly návrháře shaderů](../designers/shader-designer-nodes.md)|Tento článek popisuje typy uzlech návrháře shaderu, které vám umožní dosáhnout grafické efekty.|  
|[Příklady návrháře shaderů](../designers/shader-designer-examples.md)|Obsahuje odkazy na témata, které ukazují, jak používat návrháře shaderu k dosažení běžné grafické efekty.|
