# 实验目的
## 分析学生选课系统
### 使用GUI窗体及其组件设计窗体界面
业务要求
内容：系统角色分析及类设计
例如：学校有“人员”，分为“教师”和“学生”，教师教授“课程”，学生选择课程。
* 定义每种角色人员的属性，及其操作方法。
* 属性示例：	人员（编号、姓名、性别……）
* 教师（编号、姓名、性别、所授课程、……）
*学生（编号、姓名、性别、所选课程、……）
*课程（编号、课程名称、上课地点、时间、授课教师、……）
*以上属性仅为示例，同学们可以自行扩展。


## 二、要求:
*1、设计GUI窗体，支持学生注册、课程新加、学生选课、学生退课、打印学生选课列表等操作。
*2、基于事件模型对业务逻辑编程，实现在界面上支持上述操作。
*3、针对操作过程中可能会出现的各种异常，做异常处理
*4、基于输入/输出编程，支持学生、课程、教师等数据的读写操作。
*5、基于Github.com提交实验，包括实验SRC源文件夹程序、README.MD实验报告文档。
*6、本次实验是综合性实验，在40%的实验成绩中占比最大，望同学们认真对待。
*7、提交截止时间：12月8日。
## 三、代码：
### 登录界面代码
public class LogOnDao {
	/**
	 * 登录验证
	 * @param con
	 * @param student
	 * @return
	 * @throws Exception
	 */
public Student login(Connection con,Student student)throws Exception{
	Student resultStu=null;
	String sql="select * from t_slogon where Sno=? and Spassword=?";
PreparedStatement pstmt=con.prepareStatement(sql);
pstmt.setInt(1,student.getSno());
System.out.println(student.getSno());


pstmt.setString(2, student.getSpassword());
ResultSet rs=pstmt.executeQuery();
if(rs.next()){
	resultStu=new Student();
	resultStu.setSno(rs.getInt("Sno"));
	resultStu.setSpassword(rs.getString("Spassword"));
	
}
return resultStu;

	}
public Admin login(Connection con,Admin admin)throws Exception{
	Admin resultAdmin=null;
	String sql="select * from t_adminlogon where adminId=? and password=?";
PreparedStatement pstmt=con.prepareStatement(sql);
pstmt.setInt(1,admin.getAdminId());
pstmt.setString(2,admin.getPassword());
ResultSet rs=pstmt.executeQuery();
if(rs.next()){
	resultAdmin=new Admin();
	resultAdmin.setAdminId(rs.getInt("adminId"));
	resultAdmin.setPassword(rs.getString("password"));
package com.jakey.dao;



## 实验心得：通过本次java实验，学习到了很多概念性的的东西。在课堂上学到的知识，但是在上机调试的时候还是遇到了很多问题，很多错误是难以体会的，有时是输入的错误，这种错误比较容易找出来，但是有些问题导入之类的，就很麻烦了。总体来说，实验还是完成了的，通过查询资料库和问同学，还需要继续完善。
