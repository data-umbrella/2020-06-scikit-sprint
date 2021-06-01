# Workflow: Contributing


## PART A:  Select issue
- Pick an issue to work on:  https://github.com/scikit-learn/scikit-learn/issues
- Comment on issue with:  *I'm working on this*

### To fetch (someone else's) PR:
```bash
git fetch https://github.com/theirusername/reponame.git theirbranch:ourbranch
```

---

## PART B:  Fixing issue
- Explore and fix issue.  This will take the majority of time (!)
- Make updates to file `<file_name>`


---

## PART C:  Committing change 

#### Create feature branch

```bash
git checkout -b <feature_branch>
```

#### Commit changes to branch
Please include **(#DataUmbrella)** in your PR so we can track them.  
 
```bash
git add <file_name>
git commit -m 'description for fix'
```

---

## PART D:  Run tests

#### `flake8` formatting test
- `flake8` tests for formatting errors

```bash
flake8 <file_name>
```

#### `pytest sklearn` tests
- The [full test suite](http://scikit-learn.org/stable/developers/tips.html) takes fairly long to run
- Run tests  
```bash
pytest sklearn
```

This is an **example** of the output of a *successful* `pytest sklearn`:  [pytest_sklearn_output](pytest_sklearn_output.md)

### Create test file

#### Run tests on individual test files  
- Create test file under `tests` directory
- Run test file

```bash
pytest <test_file>
```

>example
```bash
pytest /Users/reshamashaikh/scikit-learn/sklearn/metrics/tests/test_classifier.py
pytest /Users/reshamashaikh/scikit-learn/sklearn/metrics/tests/test_mixture.py
```

This is an **example** of the output of a *successful* `pytest test_classification.py`:  
```bash
(sklearndev) % pytest sklearn/metrics/tests/test_classification.py
============================================================ test session starts ============================================================
platform darwin -- Python 3.7.1, pytest-4.0.0, py-1.7.0, pluggy-0.8.0
rootdir: /Users/reshamashaikh/scikit-learn, inifile: setup.cfg
collected 75 items                                                                                                                          

sklearn/metrics/tests/test_classification.py ...........................................................................              [100%]

=================================================== 75 passed, 3 warnings in 9.49 seconds ===================================================
(sklearndev) %
```

---

## PART E:  Submit Pull Request
### After all tests have passed, push update file(s) to feature branch
- `test_file` should be committed to feature branch as well

```bash
git add <test_file>
git commit -m 'description for test file'
git push origin <feature_branch>
```

### Submit PR  
Do this on GitHub. 

REMINDER:  Under `Conversation [description]` include references to which **Issues** and other **PRs** that your PR is related to.  

<kbd>
<img src="images/pr_ex1_raw.png"  width="80%" height="80%" />
</kbd>


<kbd>
<img src="images/pr_ex1_md.png"  width="80%" height="80%" />
</kbd>



---

## Part F:  Regression Tests on GitHub
These tests happen automatically after a PR has been submitted:  

<p>
</p>

<kbd>
<img src="images/reg_tests.png"  width="80%" height="80%" />
</kbd>



<p>
</p>

This is what it looks like when **all the checks** have passed!  

<p>
</p>

<kbd>
<img src="images/checks_passed.png" border="5" width="70%" height="70%"/>
</kbd>


## Part G:  Next Steps
- Wait for reviews (be patient)
- Address review comments in the same branch
- Pushing to your fork will update the PR
- Reviewers will "approve" the PR or change title to [MRG + 1]
- You need **2 approvals for a merge**

This is what a **merged** icon looks like:   
<p>
</p>
<kbd>
<img src="images/merged.png" border="5" width="70%" height="70%"/>
</kbd>

## Deleting branch after your PR has been merged

```python
git branch -D feature_branch
```


---

## Returning to work

### 1.  Go into directory where scikit-learn repo has been cloned on your computer
```bash
cd scikit-learn
```

>my example:  `cd /Users/reshamashaikh/software-build/scikit-learn`

### 2.  Activate virtual environment
```python
conda activate sklearndev
```

### 3.  Sync repo before beginning work (~~`master`~~ `main` branch)
```bash
git pull upstream main
git push origin main
```

### 4.  Switch to working branch  
``` 
git checkout feature_branch
```

### 5. Update working branch files
``` 
git pull upstream main
git push origin feature_branch
```



 
