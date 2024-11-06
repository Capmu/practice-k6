### k6

- Install k6 `brew intall k6`
- Create test script `k6 new` —> **script.js** will be created
    - or `k6 new <file-name>`
- Run `k6 run script.js`
    - `k6 run --vus 10 --duration 30s script.js` This will replace the stages in the code
- Test lifecycle
    
    ```tsx
    // 1. init code
    
    export function setup() {
      // 2. setup code
    }
    
    export default function (data) {
      // 3. VU code
    }
    
    export function teardown(data) {
      // 4. teardown code
    }
    ```
    
- extendtion for dashboard: https://grafana.com/docs/k6/latest/testing-guides/injecting-faults-with-xk6-disruptor/installation/
    - export PATH=$PATH:~/go/bin
    - https://github.com/grafana/xk6-dashboard?tab=readme-ov-file
        - run with server `./k6 run --out dashboard script.js`