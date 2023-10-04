pre-commit-golang
=================

:rotating_light: Please see the project sunsetting announcement:
[Issues/98](https://github.com/dnephin/pre-commit-golang/issues/98)
:rotating_light:

----

golang hooks for http://pre-commit.com/

### Using these hooks

Add this to your `.pre-commit-config.yaml`

    - repo: https://github.com/dnephin/pre-commit-golang
      rev: master
      hooks:
        - id: go-fmt
        - id: go-vet
        - id: go-lint
        - id: go-imports
        - id: go-cyclo
          args: [-over=15]
        - id: validate-toml
        - id: no-go-testing
        - id: golangci-lint
        - id: go-critic
        - id: go-unit-tests
        - id: go-build
        - id: go-mod-tidy
        - id: go-opennota
        - id: go-deadcode
        - id: go-sec
        - id: go-revive
        - id: go-staticcheck
        - id: go-errcheck

### Available hooks

- `go-fmt` - Runs `gofmt`, requires golang
- `go-vet` - Runs `go vet`, requires golang
- `go-lint` - Runs `golint`, requires https://github.com/golang/lint but is unmaintained & deprecated in favour of [`golangci-lint`](https://github.com/golangci/golangci-lint)
- `go-imports` - Runs `goimports`, requires golang.org/x/tools/cmd/goimports
- `go-cyclo` - Runs `gocyclo`, require https://github.com/fzipp/gocyclo
- `validate-toml` - Runs `tomlv`, requires https://github.com/BurntSushi/toml/tree/master/cmd/tomlv
- `no-go-testing` - Checks that no files are using `testing.T`, if you want developers to use a different testing framework
- `golangci-lint` - run `golangci-lint run ./...`, requires [golangci-lint](https://github.com/golangci/golangci-lint)
- `go-critic` - run `gocritic check ./...`, requires [go-critic](https://github.com/go-critic/go-critic)
- `go-unit-tests` - run `go test -tags=unit -timeout 30s -short -v`
- `go-build` - run `go build`, requires golang
- `go-mod-tidy` - run `go mod tidy -v`, requires golang
- `go-mod-vendor` - run `go mod vendor`, requires golang
- `go-opennota` 
  - run `aligncheck ./...`, requires [aligncheck](https://gitlab.com/opennota/check/cmd/aligncheck) 
  - run `structcheck ./...`, requires [structcheck](https://gitlab.com/opennota/check/cmd/structcheck)
  - run `varcheck ./...` requires [varcheck](https://gitlab.com/opennota/check/cmd/varcheck)
- `go-deadcode` - run `deadcode ./...`, requires [deadcode](https://github.com/tsenart/deadcode)
- `go-sec` - run `gosec -exclude-dir vendor ./...`, requires [gosec](https://github.com/securego/gosec/v2/cmd/gosec)
- `go-revive` - run `revive -exclude ./vendor/... ./...`, requires [revive](https://github.com/mgechev/revive)
- `go-staticcheck` - run `staticcheck ./...`, requires [staticcheck](https://honnef.co/go/tools/cmd/staticcheck)
- `go-errcheck` - run `errcheck -exclude ./vendor ./...`, requires [errcheck](https://github.com/kisielk/errcheck)
