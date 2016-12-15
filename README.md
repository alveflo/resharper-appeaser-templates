# Resharper appeaser command and request templates
Generates request/command classes for Appeaser with NHibernate.

## Example
#### Request
GetFoo:
```csharp
using Appeaser;
using NHibernate;

namespace Something
{
    public class GetFoo
    {
        public class Handler : IQueryHandler<Request, Result>
        {
            private readonly ISession _session;

            public Handler(ISession session)
            {
                _session = session;
            }

            public Result Handle(Request request)
            {
                return new Result();
            }
        }

        public class Request : IQuery<Result>
        {
            public Request()
            {

            }
        }

        public class Result
        {
            public Result()
            {

            }
        }
    }
}
```
#### Command
CreateFoo:
```csharp
using Appeaser;
using NHibernate;

namespace Something
{
    public class CreateFoo
    {
        public class Handler : ICommandHandler<Command, Result>
        {
            private readonly ISession _session;

            public Handler(ISession session)
            {
                _session = session;
            }

            public Result Handle(Command command)
            {
                return new Result();
            }
        }

        public class Command : ICommand<Result>
        {
            public Command()
            {

            }
        }

        public class Result
        {
            public Result()
            {

            }
        }
    }
}
```
