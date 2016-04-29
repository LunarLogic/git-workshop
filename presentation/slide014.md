        Rebase

        • skip ex
        • gco -b california
        • echo "Chapter 4" >> book
        • git commit -am "add chapter 4"
        • echo "Chapter 5"  >> book
        • git commit -am "add chapter 5"
        • git push
        • gco master
        • echo "Foreword" >> book
        • git commit -am "add foreword"
        • echo "Index" >> book
        • git commit -am "add index"
        • gl -all
        • gco california
        • git rebase master
        • gl -all
        • git push

















































































slide 014
