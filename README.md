# first commit Readme

#include <stdio.h>
#include <string.h>
enum {
    EXIT,
    INSERT,
    SEARCH,
    DELETE,
    UPDATE,
};

// 회원정보 하나 저장할 구조체, 이름, 성별
typedef struct member{
    char name[30];
    char tel[30];
}Member;
Member arr[20] = {
    {"홍길동", "010-1234-1234"}
};

int idx = 3;
void InsertMember(){
    if(idx==20){
        printf("더 이상 저장할 공간이 없습니다\n");
        return;
    }
    printf("이름 입력 : ");
    scanf("%s",arr[idx].name);
    printf("연락처 입력 : ");
    scanf("%s",arr[idx].tel);
    idx++;
    printf("회원 정보 등록 완료\n");
}



void SearchMember(){
    char str[30];
    printf("검색할 이름 입력 : ");
    scanf("%s",str);
    for(int i=0;i<idx;i++){
        if(strcmp(arr[i].name,str) ==0){

            printf("%s %s\n", arr[i].name, arr[i].tel);
            return;
        }
    }
    printf("검색 결과가 없습니다.\n");
}

void DeleteMember(){
char str[30];
printf("삭제할 이름 입력 : ");
scanf("%s",str);
for(int i=0;i<idx;i++){
    if(strcmp(arr[i].name,str)==0){
        for(int j=i;j<idx-1;j++)
            arr[j] = arr[j+1];
        idx--;
        return;
    }
}
    printf("삭제할 데이터가 없습니다.\n");
}

