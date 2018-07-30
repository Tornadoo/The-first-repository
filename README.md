# The-first-repository
==========================
校招题目：本题目使用C ++语言完成
------------
＃将迷宫渲染为字符串
##代码引用
`myproject`
```
#include<ioatream>
using namespace std;

template<typename T,typename R>
class Maze()
{
public:
	Maze(){}
	~Maze(){}
	R *Create(T a,T b,T n,R *str,R *str2);
	R *Find(R *str,R *str2);
	R *Divi(R *str1,R *str2)
private；
	T a;
	T b;
	R arr[a][b];
	R brr[2*a+1][2*b+1];
	R str;
};

//将分割好的字符串对应到brr中，返回
R *Maze::Find(R *str,R *str2)
{
	int i = 0;
	while(str[i] !='\0')
	{
		if(str[0] == str[2])//位于同一行
		{
			str2[str[0]][str[1]] = str2[str[0]][str[3]] = 'R';
		}
		else//位于同一列
		{
			str2[str[0]][str[1]] = str2[str[2]][str[1]] = 'R';
		}
	}
	return str2;
}

//分割字符串
R *Maze::Divi(R *str1,R *str2)
{
	R * res;
	int i = 0;
	int j = 0;
	while(str[i]!='\0')
	{
		while(str1[i] != '\0' &&str1[i] != ','
		&& str1[i] != ' ' && str1[i] == ';')
		{
			res[j] = str1[i];
			++i;
		}
		res = '\0';
		Find(res,str2);
	}
	return str2;
}

R *Maze::Create(T a,T b,T n,R *str1,R *str2)
{
	//初始化
	for(int i = 0;i < 2*a+1;i++)
	{
		for(int j = 0;j < 2*b+1;j++)
		{
			des[i][j] = 'W';
		}
	}
	//分割str1
	R * des = Divi(str1);
	return des;
}

int main()
{
	Maze maze;
	cin >> maze.a >> maze.b >> endl;
	cin >> maze.str >> endl;
	R *des = maze.Create(maze.a,maze.b,maze.str,maze.brr);
	for(int i = 0;i < 2*a+1;i++)
	{
		for(int j = 0;j < 2*b+1;j++)
		{
			cout << des[i][j] << endl;
		}
	}
	return 0;
}
```
＃检查输入有效性
##将输入值的范围设置在10之内；代码引用
```
if(maze.a < 0 || maze.a > 10 || maze.b < 0 || maze.b > 10)
{
  cout << "Number out of range" << endl;
}
```
##字符串的格式应该为char*
