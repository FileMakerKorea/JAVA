				
@RequestMapping(value= {"/centerList", "/list"})
	
	public String centerList(Model model, 
			@RequestParam(value="pageNum", required=false, defaultValue="1") int pageNum,
			@RequestParam(value="type", required=false,  defaultValue="null") String type,
			@RequestParam(value="keyword", required=false,defaultValue="null") String keyword) {		
	
		Map<String, Object> modelMap = 
				centerService.centerList(pageNum, type, keyword);
		
		System.out.println(pageNum + type + keyword);
		model.addAllAttributes(modelMap);		

		return "forward:/WEB-INF/views/centerList.jsp";
	}


	@Override
	public int getBloodTotalCount(String h_id, String c_id) {
		
		Map<String, Object> paramMap = new HashMap<String, Object>();
		
		paramMap.put("h_id", h_id);
		paramMap.put("c_id", c_id);
		
		return (int) sqlSession.selectOne(NAME_SPACE + ".getBloodTotalCount", paramMap);
	}
