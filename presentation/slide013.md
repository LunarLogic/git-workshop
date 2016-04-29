        Merging 3: Back merging

        • skip ex
        • gco -b oklahoma
        • echo "a day in oklahoma" >> diary
        • git commit -am "oklahoma 1"
        • gco master
        • echo "a day in school" >> diary
        • git commit -am "shool day"
        • git merge oklahoma
        • uups CONFLICTS, lets back out
        • git merge --abort
        • gco oklahoma
        • git merge master
        • resolve conflicts
        • git add; git commit
        • gco master
        • git merge oklahoma
        • nice and easy merge (fast forward)

















































































slide 013
