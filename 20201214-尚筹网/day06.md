## 1.调整表单让表单能够提交数据

### 1.1 调整assign-role.jsp

```jsp
<!-- 调整1  action method-->
<form actionk="assign/do/role/assign.html" method="post" role="form" class="form-inline">
    <!-- 调整2 -->
	<input type="hidden" name="adminId" value="${param.adminId}">
	<input type="hidden" name="pageNum" value="${param.pageNum}">
	<input type="hidden" name="keyword" value="${param.keyword}">
	<div class="form-group">
		<label for="exampleInputPassword1">未分配角色列表</label><br>
        <!-- 调整3  name mutiple-->
		<select name="roleIdList" class="form-control" multiple="multiple" size="10" 					style="width:100px;overflow-y:auto;">
             <c:forEach items="${requestScope.unAssignRole}" var="role">
					<option value="${role.id}">${role.name}</option>
			</c:forEach>
        </select>
	</div>
    ...
    <!-- 调整4 -->
    <button id="submitBtn" type="submit" style="width: 100px;" class="btn btn-lg btn-					success btn-block" >保存</button>
</form>
```

