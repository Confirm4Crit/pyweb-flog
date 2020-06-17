# Flog

# Install Dependencies & Run Tests

You should create a virtualenv for this project.  Run pip and all commands from that virtualenv.

```
$ docker-compose up -d
$ pip install -r requirements.txt
$ pytest
..........                                         [100%]
10 passed in 2.03s
```

If all tests pass, you are ready to participate in the tutorial.

## Docker

The above assumes you have Docker & docker-compose available to setup services.  You don't have to
use docker.  You could also setup these services natively on your system and change the connection
string in app.py.
---
Notes from conf
TEst 3 end

[https://github.com/rsyring/pyweb-flog/commit/9ab92e46a411f0e9e06b950a35a86dc4c5a5aca0](https://github.com/rsyring/pyweb-flog/commit/9ab92e46a411f0e9e06b950a35a86dc4c5a5aca0)

Test 3 to 4

My solution to #1 & #2: [https://github.com/rsyring/pyweb-flog/commit/6d882cca816ab113e5d16584ce3d9afb64b8556c](https://github.com/rsyring/pyweb-flog/commit/6d882cca816ab113e5d16584ce3d9afb64b8556c)

Note that I chose to return a string from `process_profile`. That causes me problems when I work on #5 and I change to returning data. But then for #8, I come back to returning the string. This kind of iterative development is exactly what we are looking for. At each step of the way, I understand a little more about the problem and make relatively small changes to accomodate. The best architecture ends up **revealing itself** and I build up my test cases and look for an elegant and maintainable solution that solves all test cases.

It also gives me **confidence** as I refactor. As long as I trust my tests, and they aren't failing, I can be confident my refactor didn't accidentally break things. That let's me **focus** my attention during the refactor on the software architecture (solid, dry, etc.) and not on what might be breaking as a result of it.

My solution to #3 & #4: [https://github.com/rsyring/pyweb-flog/commit/aeb4b3387db252e0c168a18ea20ab2f35aef4222](https://github.com/rsyring/pyweb-flog/commit/aeb4b3387db252e0c168a18ea20ab2f35aef4222)

Actually, two commits make up my solution to 3 & 4: [https://github.com/rsyring/pyweb-flog/compare/6d882cca816ab113e5d16584ce3d9afb64b8556c...b6af9838459bf6a69af38a0e115ea983b94aac55](https://github.com/rsyring/pyweb-flog/compare/6d882cca816ab113e5d16584ce3d9afb64b8556c...b6af9838459bf6a69af38a0e115ea983b94aac55)

I move away from the string based return value in preparation for switching to HTML in the web view (but I forget to actually make that change until later).

Test 4 to 5

[https://github.com/rsyring/pyweb-flog/compare/5d0ffa424aeb2824a483a0a4b099b65d11769052...88602a6d221dadc9a1be28573cf4a2cfb0da4cae](https://github.com/rsyring/pyweb-flog/compare/5d0ffa424aeb2824a483a0a4b099b65d11769052...88602a6d221dadc9a1be28573cf4a2cfb0da4cae)

---

Baseline commit to use for all tests 4 finished and ready for test 5: [https://github.com/rsyring/pyweb-flog/commit/5d0ffa424aeb2824a483a0a4b099b65d11769052](https://github.com/rsyring/pyweb-flog/commit/5d0ffa424aeb2824a483a0a4b099b65d11769052)

---

My solutions for test 5: [https://github.com/rsyring/pyweb-flog/commit/88602a6d221dadc9a1be28573cf4a2cfb0da4cae](https://github.com/rsyring/pyweb-flog/commit/88602a6d221dadc9a1be28573cf4a2cfb0da4cae)

If you checkout the branch at that commit and run the tests, you will see it actually fails. Turns out, I had to bypass Flask-Mail's helpful feature of not sending emails live during testing. I did that with a Pytest fixture: [https://github.com/rsyring/pyweb-flog/commit/660c6abcc17824e9f9fad8faa3ca850d4d070908](https://github.com/rsyring/pyweb-flog/commit/660c6abcc17824e9f9fad8faa3ca850d4d070908)
