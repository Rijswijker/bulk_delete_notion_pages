---
layout: page
title: Empty Notion Trash
description: Bookmarklet to permanently delete all notion pages that have already been deleted.
---

# Emtpy Notion Trash

- **To Install**: Drag and drop this link<a class="bookmarklet"
href="javascript:(function()%7Basync%20function%20getSpaceId()%20%7Bresp%20%3D%20await%20fetch(%22https%3A%2F%2Fwww.notion.so%2Fapi%2Fv3%2FloadUserContent%22%2C%20%7B%22credentials%22%3A%22include%22%2C%22headers%22%3A%7B%22accept%22%3A%22*%2F*%22%2C%22cache-control%22%3A%22no-cache%22%2C%22content-type%22%3A%22application%2Fjson%22%2C%22pragma%22%3A%22no-cache%22%2C%22sec-fetch-mode%22%3A%22cors%22%2C%22sec-fetch-site%22%3A%22same-origin%22%7D%2C%22referrerPolicy%22%3A%22same-origin%22%2C%22body%22%3A%22%7B%7D%22%2C%22method%22%3A%22POST%22%2C%22mode%22%3A%22cors%22%7D)%3Bjson%20%3D%20await%20resp.json()%3BspaceId%20%3D%20Object.keys(json.recordMap.space)%5B0%5D%3Breturn%20spaceId%3B%7Dasync%20function%20getBlockIds(spaceId)%20%7Bresp%20%3D%20await%20fetch(%22https%3A%2F%2Fwww.notion.so%2Fapi%2Fv3%2Fsearch%22%2C%7B%22credentials%22%3A%22include%22%2C%22headers%22%3A%7B%22accept%22%3A%22*%2F*%22%2C%22cache-control%22%3A%22no-cache%22%2C%22content-type%22%3A%22application%2Fjson%22%2C%22pragma%22%3A%22no-cache%22%2C%22sec-fetch-mode%22%3A%22cors%22%2C%22sec-fetch-site%22%3A%22same-origin%22%7D%2C%22referrerPolicy%22%3A%22same-origin%22%2C%22body%22%3A%22%7B%5C%22type%5C%22%3A%5C%22BlocksInSpace%5C%22%2C%5C%22query%5C%22%3A%5C%22%5C%22%2C%5C%22filters%5C%22%3A%7B%5C%22isDeletedOnly%5C%22%3Atrue%2C%5C%22excludeTemplates%5C%22%3Afalse%2C%5C%22isNavigableOnly%5C%22%3Atrue%2C%5C%22requireEditPermissions%5C%22%3Afalse%2C%5C%22ancestors%5C%22%3A%5B%5D%2C%5C%22createdBy%5C%22%3A%5B%5D%2C%5C%22editedBy%5C%22%3A%5B%5D%2C%5C%22lastEditedTime%5C%22%3A%7B%7D%2C%5C%22createdTime%5C%22%3A%7B%7D%7D%2C%5C%22sort%5C%22%3A%5C%22Relevance%5C%22%2C%5C%22limit%5C%22%3A1000%2C%5C%22spaceId%5C%22%3A%5C%22%22%20%2B%20spaceId%20%2B%20%22%5C%22%2C%5C%22source%5C%22%3A%5C%22trash%5C%22%7D%22%2C%22method%22%3A%22POST%22%2C%22mode%22%3A%22cors%22%7D)%3Bjson%20%3D%20await%20resp.json()%3BblockIds%20%3D%20json.results.map((el)%20%3D%3E%20%7Breturn%20el.id%7D)%3Breturn%20blockIds%3B%7D(async%20()%3D%3E%7Bconst%20spaceId%20%3D%20await%20getSpaceId()%3BblockIds%20%3D%20await%20getBlockIds(spaceId)%3Bfor%20(const%20blockId%20of%20blockIds)%20%7Bconst%20blockIdEscaped%20%3D%20'%5C%22'%20%2B%20blockId%20%2B%20'%5C%22'%3Bawait%20fetch(%22https%3A%2F%2Fwww.notion.so%2Fapi%2Fv3%2FdeleteBlocks%22%2C%20%7B%22credentials%22%3A%22include%22%2C%22headers%22%3A%7B%22accept%22%3A%22*%2F*%22%2C%22cache-control%22%3A%22no-cache%22%2C%22content-type%22%3A%22application%2Fjson%22%2C%22pragma%22%3A%22no-cache%22%2C%22sec-fetch-mode%22%3A%22cors%22%2C%22sec-fetch-site%22%3A%22same-origin%22%7D%2C%22referrerPolicy%22%3A%22same-origin%22%2C%22body%22%3A%22%7B%5C%22blockIds%5C%22%3A%5B%22%20%2BblockIdEscaped%2B%22%5D%2C%5C%22permanentlyDelete%5C%22%3Atrue%7D%22%2C%22method%22%3A%22POST%22%2C%22mode%22%3A%22cors%22%7D)%3B%7D%7D)()%7D)()"> 
Empty Notion Trash</a> to your Bookmarks Bar. 
- **To Use**: Click on the bookmark when you are on notion.so
