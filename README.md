#include<stdio.h>
#include<iostream>
#include<stdlib.h>

typedef struct p{
	int bh;
	int mm;
	struct p *next;
}LNode,*linklist;

void Initlist(linklist &p,int n)
{
	int i,k;
	p=(LNode *)malloc(sizeof(LNode));
	printf("请输入%d个密码：",n);
	p->bh = 1;
	scanf("%d",&k);
	p->mm = k;
	p->next = p;
	linklist r = p;
	for(i=1;i<n;i++)
	{
		linklist q =(LNode *)malloc(sizeof(LNode));
		q->next = r->next;
		r->next = q;
		q->bh = i+1;
		scanf("%d",&k);
		q->mm = k;
		r = r->next;
	}
}
