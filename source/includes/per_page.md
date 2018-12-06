# PerPage

<ul>
  <li>
    参数
    <ul>
      <li>per_page 每页多少个，默认24，范围1~100</li>
      <li>page 页数</li>
    </ul>
  </li>
  <li>
    接口返回 Header (如果返回有以下Header，表示数据有分页)
    <ul>
      <li>X-SLP-Current-Page: 当前页数</li>
      <li>X-SLP-Total-Pages: 总页数</li>
      <li>X-SLP-Total-Count: 总个数</li>
    </ul>
  </li>
  <li>
    例：GET /api/v4/yaw/flows/:id/journeys?per_page=30&page=3
  </li>
</ul>
