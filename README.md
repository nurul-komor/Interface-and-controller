# Interface-and-controller

Interface
```
interface AuthenticatorInterface
{
    public function authenticate(array $credentials, string $guard);
}

```

Controller 

```
class AuthenticatorController extends Controller implements AuthenticatorInterface
{
    public function authenticate(array $credentials, string $guard): bool
    {
        $token = auth($guard)->attempt($credentials);

        return $token != null ? true : false;

    }
}
```
