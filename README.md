# The main purpose of this system is planning and tracking the output from input
# The input is time and output is metrics of various tasks.
# One function is planning and the ability to break down plannings


Category < Model
  has_many :sections

  # model
  name.string
  summary.text
  assigned_time.integer # the time assigned

end

# section is breakdown direction of one category
Section
  belongs_to :category

  has_many :actions
  content.string
  assigned_time.integer # the time assigned
  deadline.date
end

# action is quite hierarchy it breaks down from annual plan > monthly plan > weekly plan > daily plan
Action
  belongs_to :section

  has_many :metrics
  assigned_time.integer # the time assigned
end


