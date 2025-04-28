# find-combo
matlab code that find all combos of the numbers 1 through N such that no number repeat n itself or located in its own  place.

n=9;
arr=ones(1,n);
count=0;
for j=1:n
    arr(j)=n-j+1;
end
i=0;
while i==0
    arr(1)=arr(1)+1;
    for j=1:n-1
        if arr(j)>n
            if j==n
                break
            else
                arr(j)=1;
                arr(j+1)=arr(j+1)+1;
            end
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
    for j=1:n
        if arr(j)==j
            i=i+1;
        end
    end
    if i~=n
        i=0;
    end
end
