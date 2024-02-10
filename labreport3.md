# Lab Report 3 - Bugs and Commands 

## PART 1

### 1. Failure inducing program
```
import org.junit.Test;
import static org.junit.Assert.assertEquals;

public class ChatHandlerTest {

    @Test(expected = NullPointerException.class)
    public void testHandleRequest_NullURI() {
        ChatHandler handler = new ChatHandler();
        handler.handleRequest(null);
    }
}
```
