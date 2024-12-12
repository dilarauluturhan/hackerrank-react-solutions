<div align="center">
  <h1 align="center">HackerRank - React - Code Review Feedback Solution</h1>
</div>

### All categories

```
import React, { useState } from "react";

const aspects = ["Readability", "Performance", "Security", "Documentation", "Testing"];

const FeedbackSystem = () => {
  // State tanımları
  const [feedback, setFeedback] = useState(
    aspects.map(() => ({ upvotes: 0, downvotes: 0 }))
  );

  // Event handler fonksiyonları
  const handleUpvote = (index) => {
    setFeedback((prevFeedback) => {
      const updatedFeedback = [...prevFeedback];
      updatedFeedback[index].upvotes += 1;
      return updatedFeedback;
    });
  };

  const handleDownvote = (index) => {
    setFeedback((prevFeedback) => {
      const updatedFeedback = [...prevFeedback];
      updatedFeedback[index].downvotes += 1;
      return updatedFeedback;
    });
  };

  return (
    <div className="my-0 mx-auto text-center w-mx-1200">
      <div className="flex wrap justify-content-center mt-30 gap-30">
        {aspects.map((aspect, index) => (
          <div key={index} className="pa-10 w-300 card">
            <h2>{aspect}</h2>
            <div className="flex my-30 mx-0 justify-content-around">
              <button
                className="py-10 px-15"
                data-testid={`upvote-btn-${index}`}
                onClick={() => handleUpvote(index)}
              >
                👍 Upvote
              </button>
              <button
                className="py-10 px-15 danger"
                data-testid={`downvote-btn-${index}`}
                onClick={() => handleDownvote(index)}
              >
                👎 Downvote
              </button>
            </div>
            <p className="my-10 mx-0" data-testid={`upvote-count-${index}`}>
              Upvotes: <strong>{feedback[index].upvotes}</strong>
            </p>
            <p className="my-10 mx-0" data-testid={`downvote-count-${index}`}>
              Downvotes: <strong>{feedback[index].downvotes}</strong>
            </p>
          </div>
        ))}
      </div>
    </div>
  );
};

export default FeedbackSystem;
```

### Just 1 category

```
import React, { useState } from "react";

const FeedbackSystem = () => {
  const [upvotes, setUpvotes] = useState(0);
  const [downvotes, setDownvotes] = useState(0);

  const handleUpvote = () => setUpvotes(upvotes + 1);
  const handleDownvote = () => setDownvotes(downvotes + 1);

  return (
    <div className="my-0 mx-auto text-center w-mx-1200">
      <div className="flex wrap justify-content-center mt-30 gap-30">
        <div className="pa-10 w-300 card">
          <h2>Readability</h2>
          <div className="flex my-30 mx-0 justify-content-around">
            <button
              className="py-10 px-15"
              data-testid="upvote-btn-0"
              onClick={handleUpvote}
            >
              👍 Upvote
            </button>
            <button
              className="py-10 px-15 danger"
              data-testid="downvote-btn-0"
              onClick={handleDownvote}
            >
              👎 Downvote
            </button>
          </div>
          <p className="my-10 mx-0" data-testid="upvote-count-0">
            Upvotes: <strong>{upvotes}</strong>
          </p>
          <p className="my-10 mx-0" data-testid="downvote-count-0">
            Downvotes: <strong>{downvotes}</strong>
          </p>
        </div>
      </div>
    </div>
  );
};

export default FeedbackSystem;

```
