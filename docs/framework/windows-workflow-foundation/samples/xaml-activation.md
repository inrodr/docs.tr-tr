---
title: "XAML etkinleştirme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 486760e2-bb10-4ed5-8c02-fe7472498d2d
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f513b10c84de968d5a18b800037b512aad90399e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="xaml-activation"></a><span data-ttu-id="12723-102">XAML etkinleştirme</span><span class="sxs-lookup"><span data-stu-id="12723-102">XAML Activation</span></span>
<span data-ttu-id="12723-103">Bu örnek, IIS'de bildirim temelli bir iş akışı barındırma gösterilmiştir.</span><span class="sxs-lookup"><span data-stu-id="12723-103">This sample demonstrates how to host a declarative workflow in IIS.</span></span> <span data-ttu-id="12723-104">Örnek olarak adlandırılan bir temel iş akışıdır `EchoService` bir işleme sahip.</span><span class="sxs-lookup"><span data-stu-id="12723-104">The sample is a basic workflow called `EchoService` that has one operation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="12723-105">Örnekler, makinenizde zaten yüklü olabilir.</span><span class="sxs-lookup"><span data-stu-id="12723-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="12723-106">Devam etmeden önce aşağıdaki (varsayılan) dizin denetleyin.</span><span class="sxs-lookup"><span data-stu-id="12723-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="12723-107">Bu dizin mevcut değilse (indirme) gidin tüm indirmek için [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri.</span><span class="sxs-lookup"><span data-stu-id="12723-107">If this directory does not exist, go to (download page) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="12723-108">Bu örnek aşağıdaki dizinde bulunur.</span><span class="sxs-lookup"><span data-stu-id="12723-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\XAMLActivation`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="12723-109">Ayarlamak için derleme ve örnek çalıştırın</span><span class="sxs-lookup"><span data-stu-id="12723-109">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="12723-110">XAMLActivation.sln çözümde açmak [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12723-110">Open the XAMLActivation.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="12723-111">Tuşlarına basarak çözümü oluşturun **F5**.</span><span class="sxs-lookup"><span data-stu-id="12723-111">Build the solution by pressing **F5**.</span></span>  
  
3.  <span data-ttu-id="12723-112">WcfTestClient.exe çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="12723-112">Run WcfTestClient.exe.</span></span> <span data-ttu-id="12723-113">Bir komut isteminden aşağıdaki komutu yazın:</span><span class="sxs-lookup"><span data-stu-id="12723-113">From a command prompt, type in the following:</span></span>  
  
    1.  <span data-ttu-id="12723-114">CD %SystemDrive%\Program Files\Microsoft Visual Studio 10.0\Common7\IDE</span><span class="sxs-lookup"><span data-stu-id="12723-114">cd %SystemDrive%\Program Files\Microsoft Visual Studio 10.0\Common7\IDE</span></span>  
  
    2.  <span data-ttu-id="12723-115">WcfTestClient.exe çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="12723-115">Run WcfTestClient.exe.</span></span>  
  
4.  <span data-ttu-id="12723-116">Hizmetinin adresini üzerinde WcfTestClient.exe CTRL + SHIFT + A basarak ve http://localhost:56133/Service.xamlx için hizmeti adresi ayarlayarak ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="12723-116">Set the address of the service on WcfTestClient.exe by pressing CTRL+SHIFT+A and setting the service address to http://localhost:56133/Service.xamlx.</span></span>  
  
5.  <span data-ttu-id="12723-117">Hizmeti sınamak için Yankı işlemi gerçekleştirin.</span><span class="sxs-lookup"><span data-stu-id="12723-117">Perform the echo operation to test the service.</span></span>  
  
6.  <span data-ttu-id="12723-118">Hizmeti IIS DeployToIIS.Bat yönetici ayrıcalıklarıyla bir komut istemi kullanarak dağıtın.</span><span class="sxs-lookup"><span data-stu-id="12723-118">Deploy the Service in IIS using DeployToIIS.Bat in a command prompt with administrator privileges.</span></span>  
  
7.  <span data-ttu-id="12723-119">Http://localhost/XAMLActivation/Service.xamlx için istemci hizmeti adresi güncelleştirmek ve hizmeti yeniden WcfTestClient.exe kullanarak test edin.</span><span class="sxs-lookup"><span data-stu-id="12723-119">Update the service address in the client to http://localhost/XAMLActivation/Service.xamlx and test the service again using WcfTestClient.exe.</span></span>