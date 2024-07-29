## Added OwnershipControls property with ObjectOwnership set to BucketOwnerEnforced.

- The template was failing due to the error: "Bucket cannot have ACLs set with ObjectOwnership's BucketOwnerEnforced setting." The BucketOwnerEnforced setting disables ACLs, so AccessControl cannot be set. The new OwnershipControls configuration ensures bucket ownership and access management without ACLs.


  ```
  "OwnershipControls": {
          "Rules": [
            {
              "ObjectOwnership": "BucketOwnerEnforced"
            }
          ]
        }
      },
      "DeletionPolicy" : "Retain"
    }
  ```


  for more info check this <a href="https://stackoverflow.com/a/76102067">stackoverflow thread that i found</a>
