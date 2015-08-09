# quicksort




void quickSort(int l,int r,int a[])
{
    if(l>r)
        return;
    int i,j,key;//i存上界，j存下界，key关键数据；
    i=l;
    j=r;
    key=a[l];
    while(i<j)
    {
        while (key < a[j])
        {
            if(i==j)
                break;
            j--;
        }
        if(i!=j)
        {
            a[i]=a[j];
            i++;
        }
        while (key>a[i])
        {
            if(i==j)
                break;
            i++;
        }
        if(i!=j)
        {
            a[j]=a[i];
            j--;
        }
    }
    a[i]=key;
    quickSort(l, i-1, a);
    quickSort(i+1, r, a);
}

int main(int argc, const char * argv[])
{
    int a[10],i,n=10;
    
    for(i=0;i<n;i++)
        a[i]=arc4random()%100;
        printf("待排数组：");
        for(i=0;i<n;i++)
            printf("%d ",a[i]);
        printf("\n");
        quickSort(0, n-1, a);
printf("结果数组：");
        for(i=0;i<n;i++)
            printf("%d ",a[i]);
