FROM ruby:3.1.0

# Install dependencies
RUN apt-get update && \
    apt-get install -y \
        build-essential \
        nodejs \
        yarn \
        default-mysql-client \
        git

# Set up working directory
WORKDIR /app

# Copy Gemfile and install gems
COPY Gemfile Gemfile.lock ./
RUN bundle install

# Copy the rest of the application
COPY . .

# Set Rails environment
ENV RAILS_ENV=development

# Start the application
CMD ["rails", "server", "-b", "0.0.0.0"]