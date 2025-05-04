# find-combo
matlab code that find all combos of the numbers 1 through N such that no number repeat n itself or located in its own  place.

n=6;
arr=zeros(1,n);
count=0;
for j=1:n
    arr(j)=n-j+1;
end
arr(1)=n-1;
i=0;
while i==0
    arr(1)=arr(1)+1;
    for j=1:n-1
        if arr(j)>n
            arr(j)=1;
            arr(j+1)=arr(j+1)+1;
        end
    end
    err=0;
    arr1=zeros(1,n);
    for j=1:n
        if arr(j)==j || arr1(arr(j))==1
            err=1;
            break
        end
        arr1(arr(j))=1;
    end
    if err==0
        count=count+1;
    end
    if arr(n)==n
        i=1;
    end
end
